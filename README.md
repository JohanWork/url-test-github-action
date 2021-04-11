# url-test-github-action

[Github action](https://docs.github.com/en/actions) using the [url-test](https://github.com/JohanWork/url-test-github-action/pulls) library to find broken links in code and docs. The goal with this Github Action it to allow for integrating test to find broke links as part of your CI/CD pipelines. 


## How to use

Example github workflow using `url-test-github-action` :

```yaml
jobs:
  test_job:
    runs-on: ubuntu-latest
    name: Test action
    steps:
    - name: checkout files in repo
      uses: actions/checkout@master
    - name: Check broken links
      uses: JohanWork/url-test-github-action@v1.0.5
      with:
        file-types: '.md'
```

in the example only files ending with `.md` will be tested. If any broken links are found the test will break after reporting all links found which are broken. 

## Examples

Two working examples can be found here:
- [Example](https://github.com/JohanWork/url-test-github-action/pull/7) with broken links
- [Example](https://github.com/JohanWork/url-test-github-action/pull/87) with no broken links


## Future work

- Implement in go to improve speed and developer experience
- Relative imports between `.md` files