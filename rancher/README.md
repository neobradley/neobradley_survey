# Usage

* Apparently there is a version issue that will cause import existing cluster fail

* Based on [你的第一次轻量级K8S体验 —— 记一次Rancher 2.2 + K3S集成部署过程](https://blog.ilemonrain.com/docker/rancher-with-k3s.html)
    * ```
      找到原因了，是版本兼容性的问题，最终可用的版本分别是：
      docker: 18.06.3
      k3s:v0.10.0
      rancher: latest （stable版本的镜像因为还不支持k8s 1.16，会出现上述问题，见https://github.com/rancher/rancher/pull/22457）
      ```

* Double compare with 
    * [K3S Release](https://github.com/rancher/k3s/releases)
        * ```
          Release v0.10.0
          @davidnuzik davidnuzik released this on Oct 23, 2019 · 245 commits to master since this release
          ```
    * [K3D Release](https://github.com/rancher/k3d/releases)
        * ```
          v1.4.0
          @iwilltry42 iwilltry42 released this on Jan 2, 2020
          ```
        * ```
          v1.3.4
          @iwilltry42 iwilltry42 released this on Oct 21, 2019
          ```
    * [Rancher Release](https://github.com/rancher/rancher/releases)
        * ```
          Release v2.3.2
          @rancherio-gh-m rancherio-gh-m released this on Oct 29, 2019 · 340 commits to master since this release
          ```

* Thus conclude K3D version v1.4.0 and Rancher version v2.3.2 will work

* When using Rancher import, if does not work on the web instruction, can download the yml to local and manually run apply -f {path}
