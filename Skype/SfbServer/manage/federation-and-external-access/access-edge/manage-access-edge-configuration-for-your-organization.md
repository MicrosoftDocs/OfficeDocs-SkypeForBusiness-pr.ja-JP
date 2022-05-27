---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを使用して、外部ドメインまたはプロバイダーへのアクセス、リモート ユーザー アクセス、および会議への匿名ユーザー アクセスの種類を有効にする必要があります。
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674599"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>組織のアクセス エッジ構成の管理

1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを使用して、外部ドメインまたはプロバイダーへのアクセス、リモート ユーザー アクセス、および会議への匿名ユーザー アクセスの種類を有効にする必要があります。

こうしたオプションには、[**アクセス エッジ構成**] ページで構成できる次の種類のアクセスが含まれます。

  - **フェデレーションとパブリック IM 接続を有効にする**   フェデレーション パートナー ドメインへのユーザー アクセスをサポートする場合は、これを有効にします。 この設定は、[ **外部アクセス ポリシー** ] ページでグローバル スコープ、サイト スコープ、またはユーザー スコープ用に構成された SIP フェデレーションに適用されます。 フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。
    
    フェデレーション パートナーを検出する方法と、アーカイブの免責事項 (展開でアーカイブが有効になっており、通信の詳細がアーカイブされることを通知するフェデレーション連絡先への通知) が連絡先に送信されるかどうかを示すオプションが 2 つあります。
    
      - **パートナー ドメイン検出を有効にする**   このオプションを選択すると、フェデレーションできるドメインの自動検出が有効になります。 Skype for Business Serverでは、ドメイン ネーム システム (DNS) レコードを使用して、許可されたドメインの一覧に表示されていないドメインを検出し、検出されたフェデレーション パートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、および管理者設定に基づいてそのトラフィックを制限またはブロックします。 このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。 このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。 詳細については、「 [許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)」を参照してください。
    
      - **フェデレーション パートナーにアーカイブ免責事項を送信する**   このオプションを選択すると、アーカイブ免責事項メッセージをフェデレーション パートナーに送信し、通信の詳細が記録されることを通知できます。 フェデレーション パートナー ドメインとの外部通信をアーカイブする場合は、アーカイブ免責事項通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。 アーカイブの詳細については、「 [フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にする」を参照してください](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **リモート ユーザー アクセスを有効にする**  在宅勤務者や旅行中のユーザーなど、ファイアウォールの外部にいる組織内のユーザーがSkype for Business Serverに接続できるようにする場合は、このオプションを有効にします。 詳細については、「 [リモート ユーザー アクセスを有効または無効にする](enable-or-disable-remote-user-access.md)」を参照してください。

  - **匿名ユーザーが会議にアクセスできるようにする**   内部ユーザーが組織する会議に外部の匿名ユーザーを招待する場合は、このオプションを有効にします。 この設定を有効にすると、会議の匿名ユーザーのみが許可されます。

> [!NOTE]  
> 外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。 外部ユーザー アクセスのポリシーの作成、構成、および適用の詳細については、「 [組織の外部アクセス ポリシーの管理](../external-access-policies/manage-external-access-policy-for-your-organization.md)」を参照してください。

**Windows PowerShell コマンドレットを使用した Access Edge 構成情報の表示**

  - Access Edge 構成情報は、Windows PowerShellと **Get-CsAccessEdgeConfiguration** コマンドレットを使用して表示できます。 このコマンドレットは、Skype for Business Server管理シェルから実行することも、Windows PowerShellのリモート セッションから実行することもできます。 
    
    すべての Access Edge 構成設定に関する情報を表示するには、Skype for Business Server管理シェルで次のコマンドを入力し、Enter キーを押します。
    
     `Get-CsAccessEdgeConfiguration`
    
    次のような情報が表示されます。
    
    ID : グローバル<br/>
    AllowAnonymousUsers : False<br/>
    AllowFederatedUsers : False<br/>
    AllowOutsideUsers : True<br/>
    BeClearingHouse : False<br/>
    EnablePartnerDiscovery : False<br/>
    EnableArchivingDisclaimer : False<br/>
    EnableUserReplicator : True<br/>
    KeepCrlsUpToDateForPeers : True<br/>
    MarkSourceVerifiableOnOutgoingMessages : True<br/>
    OutgoingTlsCountForFederatedPartners : 4<br/>
    DiscoveredPartnerStandardRate : 20<br/>
    EnableDiscoveredPartnerContactsLimit : True<br/>
    MaxContactsPerDiscoveredPartner : 1000<br/>
    DiscoveredPartnerReportPeriodMinutes : 60<br/>
    MaxAcceptedCertificatesStored : 1000<br/>
    MaxRejectedCertificatesStored : 500<br/>
    CertificatesDeletedPercentage : 20<br/>
    RoutingMethod : UseDnsSrvRouting<br/>

