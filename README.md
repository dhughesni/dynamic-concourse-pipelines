# Playground for dynamic merging of yaml files

- https://github.com/herrjulz/aviator
- https://github.com/geofffranks/spruce
- https://github.com/herrjulz/goml

## Quickstart
```
# generate concourse pipelines
$ ./build_pipelines
SPRUCE MERGE:
        concourse-stubs/base.yaml
        concourse-stubs/resource-types.yaml
        concourse-stubs/resources.yaml
        concourse-stubs/jobs/pr-build.yaml
        concourse-stubs/jobs/main-build.yaml
        concourse-stubs/jobs/release-build.yaml
        to: output/java-mvn.yaml

SPRUCE MERGE:
        concourse-stubs/base.yaml
        concourse-stubs/resource-types.yaml
        concourse-stubs/resources.yaml
        concourse-stubs/jobs/pr-build.yaml
        concourse-stubs/jobs/main-build.yaml
        concourse-stubs/jobs/release-build.yaml
        to: output/python.yaml
```

## Use of Spruce ENV Vars
> https://github.com/geofffranks/spruce/blob/master/doc/environment-variables-and-defaults.md
- The build process uses Spruces ability to subsitute an env var for a specific value.
- Build files define the following `( grab $BUILD_CMD ))`
- The *BUILD_CMD* is exported during the [build_pipelines](build_pipelines) script
- Depending on the BUILD_TYPE then the appropritate *BUILD_CMD* is set from [build-cmds](build-cmds)
