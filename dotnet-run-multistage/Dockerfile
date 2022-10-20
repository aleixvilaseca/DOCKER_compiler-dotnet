FROM microsoft/aspnetcore:2.0 AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.0.3-sdk-jessie AS build
WORKDIR /src
COPY . .
RUN dotnet publish -o /app

FROM base AS final
COPY --from=build /app .
RUN ls /app
ENTRYPOINT ["dotnet", "helloworld-netcore2.dll"]