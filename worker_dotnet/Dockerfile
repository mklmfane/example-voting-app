# Use .NET SDK to build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-mcr
WORKDIR /app
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o out

# Runtime image
FROM mcr.microsoft.com/dotnet/runtime:6.0
WORKDIR /app
COPY --from=build-mcr /app/out .
ENTRYPOINT ["dotnet", "Worker.dll"]
