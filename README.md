# bug-renovate-poetry-two-python-versions

## Introduction

### Observed behavior

This is a mono repo. 
Renovate uses same Python version for both projects.

### Expected behavior

Each projects use its own Python version defined in pyproject.toml.

In this case,

- hm-prefect/workflows/find-taxi-top-routes is using python = "3.11.x"
- hm-spark/applications/find-taxi-top-routes is using python = "3.10.x"

## Renovate Config

```json5
{
  $schema: 'https://docs.renovatebot.com/renovate-schema.json',
  extends: [
    'config:base',
  ],
  lockFileMaintenance: {
    enabled: true,
    commitMessageExtra: '({{packageFile}})',
  },
  additionalBranchPrefix: '{{parentDir}}-',
  semanticCommitScope: '{{#if parentDir}}{{parentDir}}{{else}}deps{{/if}}',
  prHourlyLimit: 0,
}
```

## Ticket

Related with https://github.com/renovatebot/renovate/issues/20615

## Renovate Log

<details>
  <summary>Click to expand</summary>

  ```shell
DEBUG: No dangling containers to remove
INFO: Repository started
{
  "renovateVersion": "35.17.1"
}
DEBUG: Using localDir: /mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions
DEBUG: PackageFiles.clear() - Package files deleted
DEBUG: initRepo("Hongbo-Miao/bug-renovate-poetry-two-python-versions")
DEBUG: Using queue: host=api.github.com, concurrency=10
DEBUG: Hongbo-Miao/bug-renovate-poetry-two-python-versions default branch = main
DEBUG: Using app token for git init
DEBUG: Repository cache is restored from revision 13
DEBUG: Resetting npmrc
DEBUG: checkOnboarding()
DEBUG: isOnboarded()
DEBUG: Checking cached config file name
DEBUG: Existing config file confirmed
DEBUG: Repository config
{
  "fileName": "renovate.json5",
  "config": {
    "$schema": "https://docs.renovatebot.com/renovate-schema.json",
    "extends": [
      "config:base"
    ],
    "lockFileMaintenance": {
      "enabled": true,
      "commitMessageExtra": "({{packageFile}})"
    },
    "additionalBranchPrefix": "{{parentDir}}-",
    "semanticCommitScope": "{{#if parentDir}}{{parentDir}}{{else}}deps{{/if}}",
    "prHourlyLimit": 0
  }
}
DEBUG: Repo is onboarded
DEBUG: migrateAndValidate()
DEBUG: No config migration necessary
DEBUG: massaged config
{
  "config": {
    "$schema": "https://docs.renovatebot.com/renovate-schema.json",
    "extends": [
      "github>whitesource/merge-confidence:beta",
      "config:base"
    ],
    "lockFileMaintenance": {
      "enabled": true,
      "commitMessageExtra": "({{packageFile}})"
    },
    "additionalBranchPrefix": "{{parentDir}}-",
    "semanticCommitScope": "{{#if parentDir}}{{parentDir}}{{else}}deps{{/if}}",
    "prHourlyLimit": 0
  }
}
DEBUG: migrated config
{
  "config": {
    "$schema": "https://docs.renovatebot.com/renovate-schema.json",
    "extends": [
      "github>whitesource/merge-confidence:beta",
      "config:base"
    ],
    "lockFileMaintenance": {
      "enabled": true,
      "commitMessageExtra": "({{packageFile}})"
    },
    "additionalBranchPrefix": "{{parentDir}}-",
    "semanticCommitScope": "{{#if parentDir}}{{parentDir}}{{else}}deps{{/if}}",
    "prHourlyLimit": 0
  }
}
DEBUG: Setting hostRules from config
DEBUG: Found repo ignorePaths
{
  "ignorePaths": [
    "**/node_modules/**",
    "**/bower_components/**",
    "**/vendor/**",
    "**/examples/**",
    "**/__tests__/**",
    "**/test/**",
    "**/tests/**",
    "**/__fixtures__/**"
  ]
}
DEBUG: Using queue: host=api.github.com, concurrency=10
DEBUG: No vulnerability alerts found
DEBUG: No vulnerability alerts found
DEBUG: findIssue(Dependency Dashboard)
DEBUG: Retrieving issueList
DEBUG: Retrieved 1 issues
DEBUG: Found issue 1
DEBUG: No baseBranches
DEBUG: extract()
DEBUG: Cached extract result cannot be used due to base branch SHA change (old=345e0842deeb8a7463be595460e5b80cee667bda, new=0f2918eecd880dc4b7a2357a3f3c0f4b080d74e4)
DEBUG: Setting current branch to main
DEBUG: Initializing git repository into /mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions
DEBUG: Performing blobless clone
DEBUG: git clone completed
{
  "durationMs": 743
}
DEBUG: latest repository commit
{
  "latestCommit": {
    "hash": "0f2918eecd880dc4b7a2357a3f3c0f4b080d74e4",
    "date": "2023-03-22T19:53:15-07:00",
    "message": "feat: init",
    "refs": "HEAD -> main, origin/main, origin/HEAD",
    "body": "",
    "author_name": "Hongbo Miao",
    "author_email": "3375461+Hongbo-Miao@users.noreply.github.com"
  }
}
DEBUG: latest commit
{
  "branchName": "main",
  "latestCommitDate": "2023-03-22T19:53:15-07:00"
}
DEBUG: Using file match: (^|/)tasks/[^/]+\.ya?ml$ for manager ansible
DEBUG: Using file match: (^|/)requirements\.ya?ml$ for manager ansible-galaxy
DEBUG: Using file match: (^|/)galaxy\.ya?ml$ for manager ansible-galaxy
DEBUG: Using file match: (^|/)\.tool-versions$ for manager asdf
DEBUG: Using file match: azure.*pipelines?.*\.ya?ml$ for manager azure-pipelines
DEBUG: Using file match: (^|/)batect(-bundle)?\.yml$ for manager batect
DEBUG: Using file match: (^|/)batect$ for manager batect-wrapper
DEBUG: Using file match: (^|/)WORKSPACE(|\.bazel)$ for manager bazel
DEBUG: Using file match: \.bzl$ for manager bazel
DEBUG: Using file match: (^|/)\.bazelversion$ for manager bazelisk
DEBUG: Using file match: \.bicep$ for manager bicep
DEBUG: Using file match: (^|/)\.?bitbucket-pipelines\.ya?ml$ for manager bitbucket-pipelines
DEBUG: Using file match: buildkite\.ya?ml for manager buildkite
DEBUG: Using file match: \.buildkite/.+\.ya?ml$ for manager buildkite
DEBUG: Using file match: (^|/)Gemfile$ for manager bundler
DEBUG: Using file match: \.cake$ for manager cake
DEBUG: Using file match: (^|/)Cargo\.toml$ for manager cargo
DEBUG: Using file match: (^|/)\.circleci/config\.yml$ for manager circleci
DEBUG: Using file match: (^|/)cloudbuild\.ya?ml for manager cloudbuild
DEBUG: Using file match: (^|/)Podfile$ for manager cocoapods
DEBUG: Using file match: (^|/)([\w-]*)composer\.json$ for manager composer
DEBUG: Using file match: (^|/)conanfile\.(txt|py)$ for manager conan
DEBUG: Using file match: (^|/)(?:deps|bb)\.edn$ for manager deps-edn
DEBUG: Using file match: (^|/)(?:docker-)?compose[^/]*\.ya?ml$ for manager docker-compose
DEBUG: Using file match: (^|/|\.)(Docker|Container)file$ for manager dockerfile
DEBUG: Using file match: (^|/)(Docker|Container)file[^/]*$ for manager dockerfile
DEBUG: Using file match: (^|/)\.drone\.yml$ for manager droneci
DEBUG: Using file match: (^|/)fleet\.ya?ml for manager fleet
DEBUG: Using file match: (^|/)flux-system/(?:.+/)?gotk-components\.yaml$ for manager flux
DEBUG: Using file match: (^|/)\.fvm/fvm_config\.json$ for manager fvm
DEBUG: Using file match: (^|/)\.gitmodules$ for manager git-submodules
DEBUG: Using file match: ^(workflow-templates|\.github/workflows)/[^/]+\.ya?ml$ for manager github-actions
DEBUG: Using file match: (^|/)action\.ya?ml$ for manager github-actions
DEBUG: Using file match: \.gitlab-ci\.yml$ for manager gitlabci
DEBUG: Using file match: \.gitlab-ci\.yml$ for manager gitlabci-include
DEBUG: Using file match: (^|/)go\.mod$ for manager gomod
DEBUG: Using file match: \.gradle(\.kts)?$ for manager gradle
DEBUG: Using file match: (^|/)gradle\.properties$ for manager gradle
DEBUG: Using file match: (^|/)gradle/.+\.toml$ for manager gradle
DEBUG: Using file match: \.versions\.toml$ for manager gradle
DEBUG: Using file match: (^|/)versions.props$ for manager gradle
DEBUG: Using file match: (^|/)versions.lock$ for manager gradle
DEBUG: Using file match: (^|/)gradle/wrapper/gradle-wrapper\.properties$ for manager gradle-wrapper
DEBUG: Using file match: (^|/)requirements\.yaml$ for manager helm-requirements
DEBUG: Using file match: (^|/)values\.yaml$ for manager helm-values
DEBUG: Using file match: (^|/)helmfile\.yaml$ for manager helmfile
DEBUG: Using file match: (^|/)Chart\.yaml$ for manager helmv3
DEBUG: Using file match: (^|/)bin/hermit$ for manager hermit
DEBUG: Using file match: ^Formula/[^/]+[.]rb$ for manager homebrew
DEBUG: Using file match: \.html?$ for manager html
DEBUG: Using file match: (^|/)plugins\.(txt|ya?ml)$ for manager jenkins
DEBUG: Using file match: (^|/)jsonnetfile\.json$ for manager jsonnet-bundler
DEBUG: Using file match: ^.+\.main\.kts$ for manager kotlin-script
DEBUG: Using file match: (^|/)kustomization\.ya?ml$ for manager kustomize
DEBUG: Using file match: (^|/)project\.clj$ for manager leiningen
DEBUG: Using file match: (^|/|\.)pom\.xml$ for manager maven
DEBUG: Using file match: ^(((\.mvn)|(\.m2))/)?settings\.xml$ for manager maven
DEBUG: Using file match: (^|\/).mvn/wrapper/maven-wrapper.properties$ for manager maven-wrapper
DEBUG: Using file match: (^|/)package\.js$ for manager meteor
DEBUG: Using file match: (^|/)Mintfile$ for manager mint
DEBUG: Using file match: (^|/)mix\.exs$ for manager mix
DEBUG: Using file match: (^|/)flake\.nix$ for manager nix
DEBUG: Using file match: (^|/)\.node-version$ for manager nodenv
DEBUG: Using file match: (^|/)package\.json$ for manager npm
DEBUG: Using file match: \.(?:cs|fs|vb)proj$ for manager nuget
DEBUG: Using file match: \.(?:props|targets)$ for manager nuget
DEBUG: Using file match: (^|/)dotnet-tools\.json$ for manager nuget
DEBUG: Using file match: (^|/)global\.json$ for manager nuget
DEBUG: Using file match: (^|/)\.nvmrc$ for manager nvm
DEBUG: Using file match: (^|/)src/main/features/.+\.json$ for manager osgi
DEBUG: Using file match: (^|/)([\w-]*)requirements\.(txt|pip)$ for manager pip_requirements
DEBUG: Using file match: (^|/)setup\.py$ for manager pip_setup
DEBUG: Using file match: (^|/)Pipfile$ for manager pipenv
DEBUG: Using file match: (^|/)pyproject\.toml$ for manager poetry
DEBUG: Using file match: (^|/)\.pre-commit-config\.yaml$ for manager pre-commit
DEBUG: Using file match: (^|/)pubspec\.ya?ml$ for manager pub
DEBUG: Using file match: (^|/)Puppetfile$ for manager puppet
DEBUG: Using file match: (^|/)\.python-version$ for manager pyenv
DEBUG: Using file match: (^|/)\.ruby-version$ for manager ruby-version
DEBUG: Using file match: \.sbt$ for manager sbt
DEBUG: Using file match: project/[^/]*\.scala$ for manager sbt
DEBUG: Using file match: project/build\.properties$ for manager sbt
DEBUG: Using file match: (^|/)setup\.cfg$ for manager setup-cfg
DEBUG: Using file match: (^|/)Package\.swift for manager swift
DEBUG: Using file match: \.tf$ for manager terraform
DEBUG: Using file match: (^|/)\.terraform-version$ for manager terraform-version
DEBUG: Using file match: (^|/)terragrunt\.hcl$ for manager terragrunt
DEBUG: Using file match: (^|/)\.terragrunt-version$ for manager terragrunt-version
DEBUG: Using file match: \.tflint\.hcl$ for manager tflint-plugin
DEBUG: Using file match: ^\.travis\.yml$ for manager travis
DEBUG: Using file match: (^|/)\.vela\.ya?ml$ for manager velaci
DEBUG: Using file match: ^\.woodpecker(?:/[^/]+)?\.ya?ml$ for manager woodpecker
DEBUG: Matched 2 file(s) for manager poetry: hm-prefect/workflows/find-taxi-top-routes/pyproject.toml, hm-spark/applications/find-taxi-top-routes/pyproject.toml
DEBUG: manager extract durations (ms)
{
  "managers": {
    "poetry": 59
  }
}
DEBUG: Found poetry package files
DEBUG: Found 2 package file(s)
INFO: Dependency extraction complete
{
  "baseBranch": "main",
  "stats": {
    "managers": {
      "poetry": {
        "fileCount": 2,
        "depCount": 10
      }
    },
    "total": {
      "fileCount": 2,
      "depCount": 10
    }
  }
}
DEBUG: Using queue: host=pypi.org, concurrency=10
DEBUG: PackageFiles.add() - Package file saved for base branch
{
  "baseBranch": "main"
}
DEBUG: Package releases lookups complete
{
  "baseBranch": "main"
}
DEBUG: branchifyUpgrades
DEBUG: detectSemanticCommits()
DEBUG: getCommitMessages
DEBUG: semanticCommits: detected "angular"
DEBUG: semanticCommits: enabled
DEBUG: 4 flattened updates found: poethepoet, poethepoet
DEBUG: Returning 2 branch(es)
DEBUG: config.repoIsOnboarded=true
DEBUG: packageFiles with updates
{
  "baseBranch": "main",
  "config": {
    "poetry": [
      {
        "deps": [
          {
            "depName": "pandas",
            "depType": "dependencies",
            "currentValue": "1.5.3",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "1.5.3",
            "versioning": "pep440",
            "updates": [],
            "packageName": "pandas",
            "warnings": [],
            "sourceUrl": "https://github.com/pandas-dev/pandas",
            "registryUrl": "https://pypi.org/pypi",
            "homepage": "https://pandas.pydata.org",
            "currentVersion": "1.5.3",
            "fixedVersion": "1.5.3"
          },
          {
            "depName": "prefect",
            "depType": "dependencies",
            "currentValue": "2.8.6",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "2.8.6",
            "versioning": "pep440",
            "updates": [],
            "packageName": "prefect",
            "warnings": [],
            "sourceUrl": "https://github.com/PrefectHQ/prefect",
            "registryUrl": "https://pypi.org/pypi",
            "homepage": "https://www.prefect.io",
            "changelogUrl": "https://github.com/PrefectHQ/prefect/blob/main/RELEASE-NOTES.md",
            "currentVersion": "2.8.6",
            "fixedVersion": "2.8.6"
          },
          {
            "depName": "prefect-aws",
            "depType": "dependencies",
            "currentValue": "0.2.5",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "0.2.5",
            "versioning": "pep440",
            "updates": [],
            "packageName": "prefect-aws",
            "warnings": [],
            "sourceUrl": "https://github.com/PrefectHQ/prefect-aws",
            "registryUrl": "https://pypi.org/pypi",
            "currentVersion": "0.2.5",
            "fixedVersion": "0.2.5"
          },
          {
            "depName": "pyarrow",
            "depType": "dependencies",
            "currentValue": "11.0.0",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "11.0.0",
            "versioning": "pep440",
            "updates": [],
            "packageName": "pyarrow",
            "warnings": [],
            "sourceUrl": "https://github.com/apache/arrow",
            "registryUrl": "https://pypi.org/pypi",
            "homepage": "https://arrow.apache.org/",
            "currentVersion": "11.0.0",
            "fixedVersion": "11.0.0"
          },
          {
            "depName": "pydantic",
            "depType": "dependencies",
            "currentValue": "1.10.7",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "1.10.7",
            "versioning": "pep440",
            "updates": [],
            "packageName": "pydantic",
            "warnings": [],
            "sourceUrl": "https://github.com/pydantic/pydantic",
            "registryUrl": "https://pypi.org/pypi",
            "currentVersion": "1.10.7",
            "fixedVersion": "1.10.7"
          },
          {
            "depName": "poethepoet",
            "depType": "dev",
            "currentValue": "0.18.1",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "0.18.1",
            "versioning": "pep440",
            "updates": [
              {
                "bucket": "non-major",
                "newVersion": "0.19.0",
                "newValue": "0.19.0",
                "releaseTimestamp": "2023-03-22T21:51:23.000Z",
                "newMajor": 0,
                "newMinor": 19,
                "updateType": "minor",
                "branchName": "renovate/find-taxi-top-routes-poethepoet-0.x"
              }
            ],
            "packageName": "poethepoet",
            "warnings": [],
            "sourceUrl": "https://github.com/nat-n/poethepoet",
            "registryUrl": "https://pypi.org/pypi",
            "currentVersion": "0.18.1",
            "isSingleVersion": true,
            "fixedVersion": "0.18.1"
          },
          {
            "depName": "pytest",
            "depType": "dev",
            "currentValue": "7.2.2",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "7.2.2",
            "versioning": "pep440",
            "updates": [],
            "packageName": "pytest",
            "warnings": [],
            "sourceUrl": "https://github.com/pytest-dev/pytest",
            "registryUrl": "https://pypi.org/pypi",
            "homepage": "https://docs.pytest.org/en/latest/",
            "changelogUrl": "https://docs.pytest.org/en/stable/changelog.html",
            "currentVersion": "7.2.2",
            "fixedVersion": "7.2.2"
          },
          {
            "depName": "pytest-cov",
            "depType": "dev",
            "currentValue": "4.0.0",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "4.0.0",
            "versioning": "pep440",
            "updates": [],
            "packageName": "pytest-cov",
            "warnings": [],
            "sourceUrl": "https://github.com/pytest-dev/pytest-cov",
            "registryUrl": "https://pypi.org/pypi",
            "changelogUrl": "https://pytest-cov.readthedocs.io/en/latest/changelog.html",
            "currentVersion": "4.0.0",
            "fixedVersion": "4.0.0"
          }
        ],
        "lockFiles": [
          "hm-prefect/workflows/find-taxi-top-routes/poetry.lock"
        ],
        "packageFile": "hm-prefect/workflows/find-taxi-top-routes/pyproject.toml",
        "constraints": {
          "python": "3.11.x"
        }
      },
      {
        "deps": [
          {
            "depName": "pyspark",
            "depType": "dependencies",
            "currentValue": "3.3.2",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "3.3.2",
            "versioning": "pep440",
            "updates": [],
            "packageName": "pyspark",
            "warnings": [],
            "sourceUrl": "https://github.com/apache/spark",
            "registryUrl": "https://pypi.org/pypi",
            "homepage": "https://github.com/apache/spark/tree/master/python",
            "currentVersion": "3.3.2",
            "fixedVersion": "3.3.2"
          },
          {
            "depName": "poethepoet",
            "depType": "dev",
            "currentValue": "0.18.1",
            "managerData": {
              "nestedVersion": false
            },
            "datasource": "pypi",
            "lockedVersion": "0.18.1",
            "versioning": "pep440",
            "updates": [
              {
                "bucket": "non-major",
                "newVersion": "0.19.0",
                "newValue": "0.19.0",
                "releaseTimestamp": "2023-03-22T21:51:23.000Z",
                "newMajor": 0,
                "newMinor": 19,
                "updateType": "minor",
                "branchName": "renovate/find-taxi-top-routes-poethepoet-0.x"
              }
            ],
            "packageName": "poethepoet",
            "warnings": [],
            "sourceUrl": "https://github.com/nat-n/poethepoet",
            "registryUrl": "https://pypi.org/pypi",
            "currentVersion": "0.18.1",
            "isSingleVersion": true,
            "fixedVersion": "0.18.1"
          }
        ],
        "lockFiles": [
          "hm-spark/applications/find-taxi-top-routes/poetry.lock"
        ],
        "packageFile": "hm-spark/applications/find-taxi-top-routes/pyproject.toml",
        "constraints": {
          "python": "3.10.x"
        }
      }
    ]
  }
}
DEBUG: detectSemanticCommits()
DEBUG: semanticCommits: returning "enabled" from cache
DEBUG: processRepo()
DEBUG: Processing 2 branches: renovate/find-taxi-top-routes-lock-file-maintenance, renovate/find-taxi-top-routes-poethepoet-0.x
DEBUG: Calculating prConcurrentLimit (10)
DEBUG: getBranchPr(renovate/find-taxi-top-routes-poethepoet-0.x)
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, open)
DEBUG: getPrList success
{
  "pullsTotal": 0,
  "requestsTotal": 1,
  "apiQuotaAffected": true
}
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, closed)
DEBUG: getBranchPr(renovate/find-taxi-top-routes-lock-file-maintenance)
DEBUG: findPr(renovate/find-taxi-top-routes-lock-file-maintenance, undefined, open)
DEBUG: findPr(renovate/find-taxi-top-routes-lock-file-maintenance, undefined, closed)
DEBUG: 0 PRs are currently open
DEBUG: PR concurrent limit remaining: 10
DEBUG: Calculated maximum PRs remaining this run: 10
DEBUG: PullRequests limit = 10
DEBUG: Calculating branchConcurrentLimit (10)
DEBUG: 0 already existing branches found:
DEBUG: Branch concurrent limit remaining: 10
DEBUG: Calculated maximum branches remaining this run: 10
DEBUG: Branches limit = 10
DEBUG: syncBranchState()(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: syncBranchState(): Branch cache not found, creating minimal branchState(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: getBranchPr(renovate/find-taxi-top-routes-poethepoet-0.x)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, open)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, closed)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: branchExists=false(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: recreateClosed is false(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, chore(find-taxi-top-routes): update dependency poethepoet to v0.19.0, !open)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: prAlreadyExisted=false(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Checking schedule(at any time, null)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: No schedule defined(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Branch needs creating(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Using reuseExistingBranch: false(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting current branch to main(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: latest commit(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "branchName": "main",
  "latestCommitDate": "2023-03-22T19:53:15-07:00"
}
DEBUG: manager.getUpdatedPackageFiles() reuseExistingBranch=false(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Starting search at index 230(packageFile="hm-spark/applications/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "depName": "poethepoet"
}
DEBUG: Found match at index 230(packageFile="hm-spark/applications/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "depName": "poethepoet"
}
DEBUG: Contents updated(packageFile="hm-spark/applications/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "depName": "poethepoet"
}
DEBUG: Value is not updated(packageFile="hm-prefect/workflows/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "manager": "poetry",
  "expectedValue": "0.19.0",
  "foundValue": "0.18.1"
}
DEBUG: Starting search at index 310(packageFile="hm-prefect/workflows/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "depName": "poethepoet"
}
DEBUG: Found match at index 310(packageFile="hm-prefect/workflows/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "depName": "poethepoet"
}
DEBUG: Contents updated(packageFile="hm-prefect/workflows/find-taxi-top-routes/pyproject.toml", branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "depName": "poethepoet"
}
DEBUG: poetry.updateArtifacts(hm-spark/applications/find-taxi-top-routes/pyproject.toml)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Updating hm-spark/applications/find-taxi-top-routes/poetry.lock(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Using python constraint from config(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting CONTAINERBASE_CACHE_DIR to /tmp/containerbase(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Using docker to execute(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "image": "sidecar"
}
DEBUG: Resolved stable matching version(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "toolName": "python",
  "constraint": "3.11.x",
  "resolvedVersion": "3.11.2"
}
DEBUG: Resolved stable matching version(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "toolName": "poetry",
  "constraint": null,
  "resolvedVersion": "1.4.1"
}
DEBUG: containerbaseDir is separate from cacheDir(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Resolved tag constraint(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "image": "docker.io/containerbase/sidecar"
}
DEBUG: Docker image is already prefetched: docker.io/containerbase/sidecar@sha256:2cf35b6530dcf59fd00ec9da371924e4bafdf0c531d604820d1a16869ad4fbc0(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Executing command(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "command": "docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\""
}
DEBUG: rawExec err(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "err": {
    "cmd": "/bin/sh -c docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\"",
    "stderr": "The currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n",
    "stdout": "installing v2 tool python v3.11.2\nlinking tool python v3.11.2\nPython 3.11.2\npip 23.0.1 from /opt/buildpack/tools/python/3.11.2/lib/python3.11/site-packages/pip (python 3.11)\nInstalled v2 /usr/local/buildpack/tools/v2/python.sh in 8 seconds\ninstalling v2 tool poetry v1.4.1\nlinking tool poetry v1.4.1\nPoetry (version 1.4.1)\nInstalled v2 /usr/local/buildpack/tools/v2/poetry.sh in 11 seconds\n",
    "options": {
      "cwd": "/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes",
      "encoding": "utf-8",
      "env": {
        "PIP_CACHE_DIR": "/tmp/renovate-cache/others/pip",
        "HOME": "/home/ubuntu",
        "PATH": "/home/ubuntu/.local/bin:/home/ubuntu/bin:/opt/buildpack/tools/python/3.9.3/bin:/home/ubuntu/.npm-global/bin:/home/ubuntu/renovateapp/node_modules/.bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
        "LC_ALL": "C.UTF-8",
        "LANG": "C.UTF-8",
        "BUILDPACK_CACHE_DIR": "/tmp/containerbase",
        "CONTAINERBASE_CACHE_DIR": "/tmp/containerbase"
      },
      "maxBuffer": 10485760,
      "timeout": 900000
    },
    "exitCode": 1,
    "name": "ExecError",
    "message": "Command failed: docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\"\nThe currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n",
    "stack": "ExecError: Command failed: docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\"\nThe currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n\n    at ChildProcess.<anonymous> (/home/ubuntu/renovateapp/node_modules/renovate/dist/util/exec/common.js:87:24)\n    at ChildProcess.emit (node:events:525:35)\n    at ChildProcess.emit (node:domain:489:12)\n    at Process.ChildProcess._handle.onexit (node:internal/child_process:293:12)"
  },
  "durationMs": 22798
}
DEBUG: Failed to update hm-spark/applications/find-taxi-top-routes/poetry.lock file(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "err": {
    "cmd": "/bin/sh -c docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\"",
    "stderr": "The currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n",
    "stdout": "installing v2 tool python v3.11.2\nlinking tool python v3.11.2\nPython 3.11.2\npip 23.0.1 from /opt/buildpack/tools/python/3.11.2/lib/python3.11/site-packages/pip (python 3.11)\nInstalled v2 /usr/local/buildpack/tools/v2/python.sh in 8 seconds\ninstalling v2 tool poetry v1.4.1\nlinking tool poetry v1.4.1\nPoetry (version 1.4.1)\nInstalled v2 /usr/local/buildpack/tools/v2/poetry.sh in 11 seconds\n",
    "options": {
      "cwd": "/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes",
      "encoding": "utf-8",
      "env": {
        "PIP_CACHE_DIR": "/tmp/renovate-cache/others/pip",
        "HOME": "/home/ubuntu",
        "PATH": "/home/ubuntu/.local/bin:/home/ubuntu/bin:/opt/buildpack/tools/python/3.9.3/bin:/home/ubuntu/.npm-global/bin:/home/ubuntu/renovateapp/node_modules/.bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
        "LC_ALL": "C.UTF-8",
        "LANG": "C.UTF-8",
        "BUILDPACK_CACHE_DIR": "/tmp/containerbase",
        "CONTAINERBASE_CACHE_DIR": "/tmp/containerbase"
      },
      "maxBuffer": 10485760,
      "timeout": 900000
    },
    "exitCode": 1,
    "name": "ExecError",
    "message": "Command failed: docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\"\nThe currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n",
    "stack": "ExecError: Command failed: docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-spark/applications/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\"\nThe currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n\n    at ChildProcess.<anonymous> (/home/ubuntu/renovateapp/node_modules/renovate/dist/util/exec/common.js:87:24)\n    at ChildProcess.emit (node:events:525:35)\n    at ChildProcess.emit (node:domain:489:12)\n    at Process.ChildProcess._handle.onexit (node:internal/child_process:293:12)"
  }
}
DEBUG: poetry.updateArtifacts(hm-prefect/workflows/find-taxi-top-routes/pyproject.toml)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Updating hm-prefect/workflows/find-taxi-top-routes/poetry.lock(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Using python constraint from config(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting CONTAINERBASE_CACHE_DIR to /tmp/containerbase(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Using docker to execute(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "image": "sidecar"
}
DEBUG: Resolved stable matching version(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "toolName": "python",
  "constraint": "3.11.x",
  "resolvedVersion": "3.11.2"
}
DEBUG: Resolved stable matching version(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "toolName": "poetry",
  "constraint": null,
  "resolvedVersion": "1.4.1"
}
DEBUG: containerbaseDir is separate from cacheDir(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Resolved tag constraint(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "image": "docker.io/containerbase/sidecar"
}
DEBUG: Docker image is already prefetched: docker.io/containerbase/sidecar@sha256:2cf35b6530dcf59fd00ec9da371924e4bafdf0c531d604820d1a16869ad4fbc0(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Executing command(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "command": "docker run --rm --name=renovate_sidecar --label=renovate_child -v \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\":\"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions\" -v \"/tmp/renovate-cache\":\"/tmp/renovate-cache\" -v \"/tmp/containerbase\":\"/tmp/containerbase\" -e PIP_CACHE_DIR -e BUILDPACK_CACHE_DIR -e CONTAINERBASE_CACHE_DIR -w \"/mnt/renovate/gh/Hongbo-Miao/bug-renovate-poetry-two-python-versions/hm-prefect/workflows/find-taxi-top-routes\" docker.io/containerbase/sidecar bash -l -c \"install-tool python 3.11.2 && install-tool poetry 1.4.1 && poetry update --lock --no-interaction poethepoet\""
}
DEBUG: exec completed(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "durationMs": 32279,
  "stdout": "installing v2 tool python v3.11.2\nlinking tool python v3.11.2\nPython 3.11.2\npip 23.0.1 from /opt/buildpack/tools/python/3.11.2/lib/python3.11/site-packages/pip (python 3.11)\nInstalled v2 /usr/local/buildpack/tools/v2/python.sh in 9 seconds\ninstalling v2 tool poetry v1.4.1\nlinking tool poetry v1.4.1\nPoetry (version 1.4.1)\nInstalled v2 /usr/local/buildpack/tools/v2/poetry.sh in 11 seconds\nUpdating dependencies\nResolving dependencies...\n\nWriting lock file\n  • Installing certifi (2022.12.7)\n  • Installing charset-normalizer (3.1.0)\n  • Installing idna (3.4)\n  • Installing sniffio (1.3.0)\n  • Installing six (1.16.0)\n  • Installing tzdata (2022.7)\n  • Installing urllib3 (1.26.15)\n  • Installing pyasn1 (0.4.8)\n  • Installing anyio (3.6.2)\n  • Installing hyperframe (6.0.1)\n  • Installing jmespath (1.0.1)\n  • Installing cachetools (5.3.0)\n  • Installing h11 (0.14.0)\n  • Installing markupsafe (2.1.2)\n  • Installing pycparser (2.21)\n  • Installing oauthlib (3.2.2)\n  • Installing python-dateutil (2.8.2)\n  • Installing pytz-deprecation-shim (0.1.0.post0)\n  • Installing requests (2.28.2)\n  • Installing rsa (4.9)\n  • Installing typing-extensions (4.5.0)\n  • Installing hpack (4.0.0)\n  • Installing pyasn1-modules (0.2.8)\n  • Installing mdurl (0.1.2)\n  • Installing attrs (22.2.0)\n  • Installing cffi (1.15.1)\n  • Installing click (8.1.3)\n  • Installing colorama (0.4.6)\n  • Installing google-auth (2.16.2)\n  • Installing greenlet (2.0.2)\n  • Installing h2 (4.1.0)\n  • Installing httpcore (0.16.3)\n  • Installing jsonpointer (2.3)\n  • Installing mako (1.2.4)\n  • Installing markdown (3.4.1)\n  • Installing markdown-it-py (2.2.0)\n  • Installing packaging (23.0)\n  • Installing pydantic (1.10.7)\n  • Installing pygments (2.14.0)\n  • Installing pyrsistent (0.19.3)\n  • Installing pytz (2022.7.1)\n  • Installing pytzdata (2020.1)\n  • Installing pyyaml (6.0)\n  • Installing regex (2022.10.31)\n  • Installing requests-oauthlib (1.3.1)\n  • Installing rfc3986 (1.5.0)\n  • Updating setuptools (67.4.0 -> 67.6.0)\n  • Installing sqlalchemy (1.4.47)\n  • Installing starlette (0.26.1)\n  • Installing text-unidecode (1.3)\n  • Installing tzlocal (4.3)\n  • Installing websocket-client (1.5.1)\n  • Installing botocore (1.29.94)\n  • Installing aiosqlite (0.18.0)\n  • Installing asgi-lifespan (2.0.0)\n  • Installing alembic (1.10.2)\n  • Installing coolname (2.2.0)\n  • Installing croniter (1.3.8)\n  • Installing cryptography (39.0.2)\n  • Installing dateparser (1.1.7)\n  • Installing cloudpickle (2.2.1)\n  • Installing asyncpg (0.27.0)\n  • Installing fastapi (0.95.0)\n  • Installing fsspec (2023.1.0)\n  • Installing jinja2 (3.1.2)\n  • Installing jsonpatch (1.32)\n  • Installing jsonschema (4.17.3)\n  • Installing kubernetes (26.1.0)\n  • Installing orjson (3.8.7)\n  • Installing pathspec (0.11.1)\n  • Installing pendulum (2.1.2)\n  • Installing pluggy (1.0.0)\n  • Installing python-slugify (8.0.1)\n  • Installing readchar (4.0.5)\n  • Installing rich (13.3.2)\n  • Installing s3transfer (0.6.0)\n  • Installing toml (0.10.2)\n  • Installing typer (0.7.0)\n  • Installing uvicorn (0.21.1)\n  • Installing websockets (10.4)\n  • Installing httpx (0.23.3)\n  • Installing apprise (1.3.0)\n  • Installing docker (6.0.1)\n  • Installing griffe (0.25.5)\n  • Installing iniconfig (2.0.0)\n  • Installing boto3 (1.26.94)\n  • Installing coverage (7.2.2)\n  • Installing mypy-boto3-s3 (1.26.62)\n  • Installing mypy-boto3-secretsmanager (1.26.89)\n  • Installing numpy (1.24.2)\n  • Installing prefect (2.8.6)\n  • Installing tomli (2.0.1)\n  • Installing pytest (7.2.2)\n  • Installing pastel (0.2.1)\n  • Installing pandas (1.5.3)\n  • Installing poethepoet (0.19.0)\n  • Installing prefect-aws (0.2.5)\n  • Installing pytest-cov (4.0.0)\n  • Installing pyarrow (11.0.0)\n",
  "stderr": "Creating virtualenv hm-prefect-find-taxi-top-routes-UgGKWr_T-py3.11 in /home/ubuntu/.cache/pypoetry/virtualenvs\n"
}
DEBUG: Returning updated hm-prefect/workflows/find-taxi-top-routes/poetry.lock(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Updated 2 package files(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Updated 1 lock files(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "updatedArtifacts": [
    "hm-prefect/workflows/find-taxi-top-routes/poetry.lock"
  ]
}
DEBUG: Branch timestamp: 2023-03-22T21:51:23.000Z(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: PR is older than 2 hours, raise PR with lock file errors(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: 3 file(s) to commit(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Preparing files for committing to branch renovate/find-taxi-top-routes-poethepoet-0.x(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting git author name: Renovate Bot(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting git author email: bot@renovateapp.com(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: git commit(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "deletedFiles": [],
  "ignoredFiles": [],
  "result": {
    "author": null,
    "branch": "renovate/find-taxi-top-routes-poethepoet-0.x",
    "commit": "652410cc19e9e68062b51f321fb280d55997215d",
    "root": false,
    "summary": {
      "changes": 3,
      "insertions": 6,
      "deletions": 0
    }
  }
}
DEBUG: resetToCommit(0f2918eecd880dc4b7a2357a3f3c0f4b080d74e4)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Fetching branch renovate/find-taxi-top-routes-poethepoet-0.x(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting current branch to main(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: latest commit(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "branchName": "main",
  "latestCommitDate": "2023-03-22T19:53:15-07:00"
}
INFO: Branch created(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "commitSha": "443e654b1486e1caa1db5898489a0b10a8bcf07c"
}
DEBUG: Updating status check state to failed(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Setting branch status(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "context": "renovate/artifacts",
  "state": "red"
}
DEBUG: Ensuring PR(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: There are 0 errors and 0 warnings(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: getBranchPr(renovate/find-taxi-top-routes-poethepoet-0.x)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, open)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, closed)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: getPrCache()(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Forcing PR because of artifact errors(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Fetching changelog: https://github.com/nat-n/poethepoet (0.18.1 -> 0.19.0)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Fetching changelog: https://github.com/nat-n/poethepoet (0.18.1 -> 0.19.0)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Creating PR(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "prTitle": "chore(find-taxi-top-routes): update dependency poethepoet to v0.19.0"
}
DEBUG: Creating PR(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "title": "chore(find-taxi-top-routes): update dependency poethepoet to v0.19.0",
  "head": "Hongbo-Miao:renovate/find-taxi-top-routes-poethepoet-0.x",
  "base": "main",
  "draft": false
}
DEBUG: PR created(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "pr": 2,
  "draft": false
}
DEBUG: Adding labels '' to #2(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
INFO: PR created(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "pr": 2,
  "prTitle": "chore(find-taxi-top-routes): update dependency poethepoet to v0.19.0"
}
DEBUG: addParticipants(pr=2)(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: setPrCache()(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Created Pull Request #2(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
WARN: artifactErrors(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "artifactErrors": [
    {
      "lockFile": "hm-spark/applications/find-taxi-top-routes/poetry.lock",
      "stderr": "installing v2 tool python v3.11.2\nlinking tool python v3.11.2\nPython 3.11.2\npip 23.0.1 from /opt/buildpack/tools/python/3.11.2/lib/python3.11/site-packages/pip (python 3.11)\nInstalled v2 /usr/local/buildpack/tools/v2/python.sh in 8 seconds\ninstalling v2 tool poetry v1.4.1\nlinking tool poetry v1.4.1\nPoetry (version 1.4.1)\nInstalled v2 /usr/local/buildpack/tools/v2/poetry.sh in 11 seconds\n\nThe currently activated Python version 3.11.2 is not supported by the project (3.10.x).\nTrying to find and use a compatible version. \n\n[Errno 2] No such file or directory: 'python3.10'\n"
    }
  ]
}
DEBUG: Getting comments for #2(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Found 0 comments(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: Ensuring comment "⚠ Artifact update problem" in #2(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
INFO: Comment added(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
{
  "issueNo": 2,
  "topic": "⚠ Artifact update problem"
}
DEBUG: setBranchCommit()(branch="renovate/find-taxi-top-routes-poethepoet-0.x")
DEBUG: syncBranchState()(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: syncBranchState(): update baseBranchSha(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: getBranchPr(renovate/find-taxi-top-routes-lock-file-maintenance)(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: findPr(renovate/find-taxi-top-routes-lock-file-maintenance, undefined, open)(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: findPr(renovate/find-taxi-top-routes-lock-file-maintenance, undefined, closed)(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: branchExists=false(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: recreateClosed is true(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: Checking schedule(before 5am on monday, null)(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: Checking 1 schedule(s)(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: Checking schedule "before 5am on monday"(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
{
  "parsedSchedule": {
    "schedules": [
      {
        "t_b": [
          18000
        ],
        "d": [
          2
        ]
      }
    ],
    "exceptions": [],
    "error": -1
  }
}
DEBUG: Package not scheduled(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: Skipping branch creation as not within schedule(branch="renovate/find-taxi-top-routes-lock-file-maintenance")
DEBUG: getBranchPr(renovate/find-taxi-top-routes-poethepoet-0.x)
DEBUG: findPr(renovate/find-taxi-top-routes-poethepoet-0.x, undefined, open)
DEBUG: Found PR #2
DEBUG: getPrCache()
DEBUG: getPrCache()
DEBUG: Ensuring Dependency Dashboard
DEBUG: ensureIssue(Dependency Dashboard)
DEBUG: Patching issue
DEBUG: Issue updated
DEBUG: Removing any stale branches
DEBUG: config.repoIsOnboarded=true
DEBUG: Branch lists
{
  "branchList": [
    "renovate/find-taxi-top-routes-lock-file-maintenance",
    "renovate/find-taxi-top-routes-poethepoet-0.x"
  ],
  "renovateBranches": [
    "renovate/find-taxi-top-routes-poethepoet-0.x"
  ]
}
DEBUG: remainingBranches=
DEBUG: No branches to clean up
DEBUG: Cleaning up Renovate refs: refs/renovate/*
DEBUG: PackageFiles.clear() - Package files deleted
DEBUG: Branch summary
{
  "cacheModified": true,
  "baseBranches": [
    {
      "branchName": "main",
      "sha": "0f2918eecd880dc4b7a2357a3f3c0f4b080d74e4"
    }
  ],
  "branches": [
    {
      "automerge": false,
      "baseBranch": "main",
      "baseBranchSha": "0f2918eecd880dc4b7a2357a3f3c0f4b080d74e4",
      "branchName": "renovate/find-taxi-top-routes-poethepoet-0.x",
      "branchSha": "443e654b1486e1caa1db5898489a0b10a8bcf07c",
      "isModified": false,
      "isPristine": true
    }
  ],
  "inactiveBranches": [
    "renovate/find-taxi-top-routes-lock-file-maintenance"
  ]
}
DEBUG: Renovate repository PR statistics
{
  "stats": {
    "total": 1,
    "open": 1,
    "closed": 0,
    "merged": 0
  }
}
DEBUG: Repository result: done, status: onboarded, enabled: true, onboarded: true
DEBUG: Repository timing splits (milliseconds)
{
  "splits": {
    "init": 3223,
    "extract": 3316,
    "lookup": 936,
    "onboarding": 0,
    "update": 62921
  },
  "total": 72512
}
DEBUG: Package cache statistics
{
  "get": {
    "count": 13,
    "avgMs": 84,
    "medianMs": 70,
    "maxMs": 313
  },
  "set": {
    "count": 2,
    "avgMs": 23,
    "medianMs": 6,
    "maxMs": 39
  }
}
DEBUG: http statistics
{
  "urls": {
    "https://api.github.com/graphql (POST,200)": 3,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/commits/443e654b1486e1caa1db5898489a0b10a8bcf07c/statuses (GET,200)": 2,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/commits/renovate/find-taxi-top-routes-poethepoet-0.x/status (GET,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/contents/renovate.json5 (GET,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/git/commits (POST,201)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/git/refs (POST,201)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/git/trees (POST,201)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/issues/1 (GET,200)": 2,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/issues/1 (PATCH,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/issues/2/comments (GET,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/issues/2/comments (POST,201)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/pulls (GET,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/pulls (POST,201)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-poetry-two-python-versions/statuses/443e654b1486e1caa1db5898489a0b10a8bcf07c (POST,201)": 1,
    "https://api.github.com/repos/whitesource/merge-confidence/contents/beta.json (GET,200)": 1,
    "https://pypi.org/pypi/prefect-aws/json (GET,200)": 1,
    "https://pypi.org/pypi/prefect/json (GET,200)": 1
  },
  "hostStats": {
    "api.github.com": {
      "requestCount": 19,
      "requestAvgMs": 355,
      "queueAvgMs": 0
    },
    "pypi.org": {
      "requestCount": 2,
      "requestAvgMs": 369,
      "queueAvgMs": 0
    }
  },
  "totalRequests": 21
}
DEBUG: Package lookup durations
{
  "pypi": {
    "count": 10,
    "averageMs": 227,
    "totalMs": 2269,
    "maximumMs": 570
  }
}
DEBUG: dns cache
{
  "hosts": [
    "api.github.com",
    "pypi.org"
  ]
}
INFO: Repository finished
{
  "cloned": true,
  "durationMs": 72512
}
  ```
</details>
