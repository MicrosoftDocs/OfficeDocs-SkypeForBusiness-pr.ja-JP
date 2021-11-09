---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを通じて、外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、匿名ユーザー アクセスの種類を有効にする必要があります。
ms.openlocfilehash: ff152ea25bbea750815e0619ce521ede8d8d7203
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860094"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>組織のアクセス エッジ構成の管理

1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを通じて、外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、匿名ユーザー アクセスの種類を有効にする必要があります。

こうしたオプションには、[**アクセス エッジ構成**] ページで構成できる次の種類のアクセスが含まれます。

  - **フェデレーションとパブリック IM 接続を有効にする**   フェデレーション パートナー ドメインへのユーザー アクセスをサポートする場合は、これを有効にしてください。 この設定は、[外部アクセス ポリシー] ページのグローバル スコープ、サイト スコープ、またはユーザー スコープ用に構成された SIP フェデレーション **に適用** されます。 フェデレーション設定を適用するには、両方のページでフェデレーション サポートを構成する必要があります。
    
    フェデレーション パートナーの検出方法と、アーカイブに関する免責事項 (展開でアーカイブが有効になっていると通信するフェデレーション連絡先への通知、および通信の詳細がアーカイブされる) が連絡先に送信されるかどうかの 2 つのオプションがあります。
    
      - **パートナー ドメインの検出を有効にする**   このオプションを選択すると、フェデレーションできるドメインの自動検出が有効になります。 Skype for Business Serverは、ドメイン ネーム システム (DNS) レコードを使用して、許可されたドメイン リストに記載されていないドメインを検出し、検出されたフェデレーション パートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、および管理者設定に基づいてそのトラフィックを制限またはブロックします。 このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。 このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。 詳細については、「許可された [外部ドメインのサポートを構成する」を参照してください](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **フェデレーション パートナーにアーカイブの免責事項を送信する**   このオプションを選択すると、通信の詳細が記録されるという通知を提供するアーカイブ免責事項メッセージをフェデレーション パートナーに送信できます。 フェデレーション パートナー ドメインとの外部通信をアーカイブする場合は、アーカイブ免責事項通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされているパートナーに警告する必要があります。 アーカイブの詳細については、「フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にする [」を参照してください](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **リモート ユーザー アクセスを有効にする**  通信会社や出張中のユーザーなど、ファイアウォールの外部に所属する組織内のユーザーが Skype for Business Server に接続できる場合は、このオプションを有効にします。 詳細については、「リモート ユーザー アクセス [を有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。

  - **匿名ユーザーが会議にアクセスできる**   内部ユーザーが組織する会議に外部匿名ユーザーを招待する場合は、このオプションを有効にします。 この設定を有効にすると、匿名ユーザーだけが会議に参加できます。

> [!NOTE]  
> 外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。 外部ユーザー アクセス用のポリシーの作成、構成、適用の詳細については、「組織の外部アクセス ポリシーの管理」 [を参照してください](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**アクセス エッジの構成情報を表示するには、Windows PowerShellコマンドレットを使用します。**

  - Access Edge 構成情報を表示するには、Windows PowerShell **Get-CsAccessEdgeConfiguration コマンドレットを使用** します。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 
    
    すべての Access Edge 構成設定に関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
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

