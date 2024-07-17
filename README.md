# README

```text
dotnet tool install --global JetBrains.dotCover.GlobalTool

dotnet sonarscanner begin /k:"$(basename `pwd`)" /d:sonar.host.url="$SONAR_HOST_URL" /d:sonar.token="$SONAR_TOKEN" /d:sonar.cs.dotcover.reportsPaths=dotCover.Output.html && \
  dotnet build --no-incremental && \
  dotnet dotcover test --dcReportType=HTML && \
  dotnet sonarscanner end /d:sonar.token="$SONAR_TOKEN"
```

Ref: [.NET test coverage](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/test-coverage/dotnet-test-coverage/#dotcover)
