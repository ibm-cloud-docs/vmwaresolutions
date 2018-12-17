---

copyright:

  years:  2016, 2018

lastupdated: "2018-11-01"

---

# 架構概觀

本節提供此參考架構中所使用網路架構的詳細資料。它由下列各節組成：
* **VCS 概觀** - 本節說明 VCS 平台的重點。
* **網路概觀** - 這些小節提供此參照架構中所使用網路元件的相關資訊：
  - **IBM Cloud 網路** - {{site.data.keyword.cloud}} 提供實體網路，並由 {{site.data.keyword.cloud_notm}} 完全進行管理。此網路有一些需要瞭解的主要特徵，以瞭解內部部署與外部部署之間以及在不同服務中管理的工作負載之間的網路流程。
  - **NSX-V** - 具有 VMware NSX-V 所提供層疊之 {{site.data.keyword.cloud_notm}} 網路上的 VCS 網路建置。此層疊會分段來自 {{site.data.keyword.cloud_notm}} 基礎網路的資料流量，以容許更良好地控制及配置（包括 BYOIP）。
  - **IBM Kubernetes Service** - IKS 使用 Calico 作為其「容器網路介面」外掛程式。
  - **IBM Cloud Private** - ICP 使用 Calico 作為其「容器網路介面」外掛程式。

* **整合** - 本節說明網路元件的架構，以容許所需的網路資料流量及定址：
  - IP 位址配置
  - 網路資料流量

## VCS 概觀

VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle (VCS) 是一種受管理的專用雲端，可協助您快速且輕鬆地將內部部署基礎架構擴充到雲端，以實現安全且無縫的基礎架構混合及真正的應用程式行動性。

VCS Hybridity Bundle 部署在最少四部 {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} 上，透過虛擬儲存區域網路 (VSAN) 提供專用儲存空間，並包括自動部署及配置易於管理的軟體定義網路基礎架構 (NSX-V)。VCS Hybridity Bundle 是透過自動化部署的參照架構，可確保一致性、效能和相符性。在許多情況下，整個環境可以在一天內佈建完成，且裸機基礎架構可以快速而彈性地調整運算和儲存空間容量，視需要擴增及縮減。

有許多選項可用來加強及延伸 VCS Hybridity Bundle。{{site.data.keyword.cloud_notm}} 服務供應項目不僅包括附加儲存空間選項及各種公用和專用 WAN 連線功能選項，還涵蓋平台安全、網路安全、資料流量平衡到備份和災難回復等領域。

平台安全服務包括 HyTrust CloudControl on {{site.data.keyword.cloud_notm}}，其提供自動化安全和法規遵循支援，可讓您更加明瞭及掌控雲端環境和管理者。HyTrust DataControl on {{site.data.keyword.cloud_notm}} 透過強大的加密和可擴充的金鑰管理來提供資料保護，以確保工作負載整個生命週期的安全。{{site.data.keyword.cloud_notm}} Secure Virtualization 簡化了法規遵循，並透過加密、地理柵欄原則及角色型存取控制來保護資料，而 KMIP for VMware on {{site.data.keyword.cloud_notm}} 這個加密金鑰生命週期管理供應項目，則管理 {{site.data.keyword.cloud_notm}} 服務或客戶內建應用程式所使用的加密金鑰。

網路安全選項是 FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}，其佈建一對高度可用的 FortiGate Security Appliance 裝置，用來分析網路資料流量及保護虛擬基礎架構，還有 FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}，以在 {{site.data.keyword.cloud_notm}} 上部署高可用性配對的 FortiGate VM，藉由在虛擬基礎架構內實作重要安全控制來降低風險。還有其他網路安全供應項目正在開發中。

F5 on {{site.data.keyword.cloud_notm}} 網路負載平衡器服務供應項目透過 F5 BIG-IP 套組，使效能最佳化，並確保最重要應用程式的可用性及安全。

IBM、Veeam 和 Zerto 提供的備份和災難回復供應項目可在發生災難時確保持續運作，讓您高枕無憂。IBM Spectrum Protect Plus on {{site.data.keyword.cloud_notm}} 是虛擬環境的資料保護及可用性解決方案。Veeam on {{site.data.keyword.cloud_notm}} 可讓 Always-On Enterprise™ 與 {{site.data.keyword.cloud_notm}} 上的備份、回復和抄寫整合功能搭配使用。Zerto on {{site.data.keyword.cloud_notm}} 為內部部署客戶和 {{site.data.keyword.cloud_notm}} 客戶提供一個安全、有彈性且可擴充的「災難回復」解決方案。

{{site.data.keyword.cloud_notm}} VCS Hybridity Bundle 不是受管理服務，但您可以新增 IBM 管理的服務來卸載虛擬化、來賓作業系統或應用程式層的日常作業及維護工作。{{site.data.keyword.cloud_notm}} Professional Services 團隊也可以透過移轉、實作、規劃及上線服務來協助您加速邁向雲端。

VCS Hybridity Bundle 的平台整合選項未侷限於 VMware 提供的選項（例如 vRealize Suite 或 vSphere with Operations Management），但可跨越多個 {{site.data.keyword.cloud_notm}} 服務供應項目（例如 [vCenter Server 和 IBM Kubernetes](../vcsiks/vcsiks-intro.html) 及 [vCenter Server 和 {{site.data.keyword.cloud_notm}} Private](../vcsicp/vcsicp-intro.html)），使用開放程式碼 Terraform 將基礎架構當作程式碼來管理及遞送。

VCS Hybridity Bundle 適用廣泛的服務組合及多供應項目整合選項，可提供真正的混合式平台，讓 Hybridity 能夠成為服務。

### 相關鏈結

* [VCS Hybridity Bundle 概觀](../vcs/vcs-hybridity-intro.html)