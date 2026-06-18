# 建立建置階段，使用 .NET 10 SDK
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src
RUN pwd
COPY . .
RUN ls -la  # 這會把當前目錄下的檔案列出來，讓你確認是否成功 COPY 進來
# RUN dotnet restore
# 建立專案
# RUN dotnet new console -o HelloWorld
# 切換到專案目錄
WORKDIR /src/HelloWorld
# 還原並執行
#RUN dotnet run

#RUN dotnet restore
#RUN dotnet publish -c Release -o ./app/publish

# 建立執行階段，使用 .NET 10 ASP.NET 執行環境
#FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS final
#WORKDIR ./app
#EXPOSE 8080
#COPY --from=build ./app/publish .
#ENTRYPOINT ["dotnet", "helloworld.dll"]
