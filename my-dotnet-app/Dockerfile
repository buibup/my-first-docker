# 1. Build stage
FROM mcr.microsoft.com/dotnet/sdk:10.0.100-preview.5 AS build

# 2. Set working directory in image
WORKDIR /app

# 3. Copy application into image
COPY . .

# 4. Run dotnet publish to build application
RUN dotnet publish -c Release -o out

# 5. Runtime stage
FROM mcr.microsoft.com/dotnet/aspnet:10.0.0-preview.5
WORKDIR /app

# 6. Set environment variable for ASP.NET Core URLs
ENV ASPNETCORE_URLS=http://+:5000

# 7. Copy application into image
COPY --from=build /app/out ./
ENTRYPOINT ["dotnet", "my-dotnet-app.dll"]