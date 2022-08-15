# Index file
### This is the Index of the repo
#### This is a picture of  Yaktocat
![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)

```
$PAT = "ldksfskldhfksjdfkjdsfhkjsdfh"
$auth = @{Authorization = 'Basic ' + [Convert]::ToBase64String([Text.Encoding]::ASCII.GetBytes(":$($PAT)")) }
$collection = "BAH"
$project = "BAR"

$baseURI = "http://rdtfs:8080/tfs/$($collection)/$($project)/_apis/git/repositories?api-version=4.1"

$response = Invoke-RestMethod -Uri $baseURI -Method GET -Headers $auth -ContentType "application/json"
Write-Host $response


foreach ($repo in $response.value) 
{
    echo $repo.name
    $repoUrl = "http://rdtfs:8080/tfs/BAH/$($project)/_git/$($repo.name)"
    git clone $repoUrl
    
```

- [ ] Turn on GitHub Pages
- [ ] Outline my portfolio
- [ ] Introduce myself to the world
