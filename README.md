# README

```text
dotnet sonarscanner begin /k:"$(basename `pwd`)" /d:sonar.token="$SONAR_TOKEN" /d:sonar.verbose=true && \
  dotnet build --no-incremental && \
  dotnet-coverage collect dotnet test -f xml -o coverage.xml
  dotnet sonarscanner end /d:sonar.token="$SONAR_TOKEN"
```
