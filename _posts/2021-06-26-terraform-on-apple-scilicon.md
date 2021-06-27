---
layout: posts
title: "Terraform on Apple Silicon"
updated: 2021-06-26
category: posts
---


Terraform is supported on Apple Silicon, but the following error could happens when you run `terraform init`.


> Provider registry.terraform.io/hashicorp/template v2.2.0 does not have a package available for your current platform, darwin_arm64.


Relevant ticket: [https://github.com/hashicorp/terraform/issues/27257](https://github.com/hashicorp/terraform/issues/27257)

Based on `anthonynsimon`'s comment, the workaround is to locally compile terraform from source and copy & paste into a pre-defined path.

1. Install Terraform and Golang if you haven't. `brew install terraform go`
2. Clone the repo. `git clone https://github.com/hashicorp/terraform-provider-template`
3. Build from source. `go build`
4. Create the target directory if it doesn't exist. `mkdir -p ~/.terraform.d/plugins/registry.terraform.io/hashicorp/template/2.2.0/darwin_arm64/`
5. Move the binary. `mv terraform-provider-template ~/.terraform.d/plugins/registry.terraform.io/hashicorp/template/2.2.0/darwin_arm64/terraform-provider-template`
6. Make it executable. `chmod +x ~/.terraform.d/plugins/registry.terraform.io/hashicorp/template/2.2.0/darwin_arm64/terraform-provider-template`

Someone also made a CLI tool to streamline the process. [m1-terraform-provider-helper](https://github.com/kreuzwerker/m1-terraform-provider-helper)