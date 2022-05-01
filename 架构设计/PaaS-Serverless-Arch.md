# PaaS Serverless Arch

---
![PaaS Serverless架构设计](../resoure/PaaS-Serverless-Arch.jpg)

- 网关
  - Ingress
  - Egress
- Mesh
  - ServiceMesh
  - Dapr-Mesh
- Serverless
- Container(runc),*Docker -> Container -> WASM*
- Kata Container(runv),*kvm -> unikernel*
