# README

```text
dotnet tool install JetBrains.dotCover.GlobalTool -g  -a arm64

dotnet sonarscanner begin /k:"$(basename `pwd`)" /d:sonar.host.url="$SONAR_HOST_URL" /d:sonar.token="$SONAR_TOKEN" /d:sonar.cs.dotcover.reportsPaths=dotCover.Output.html /d:sonar.cs.xunit.reportsPaths="**/xunit_test_result.xml" && \
  dotnet build --no-incremental && \
  dotnet dotcover test --dcReportType=HTML --logger "xunit;LogFileName=xunit_test_result.xml" && \
  dotnet sonarscanner end /d:sonar.token="$SONAR_TOKEN"
```

Adapted from [.NET test coverage](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/test-coverage/dotnet-test-coverage/#dotcover).
