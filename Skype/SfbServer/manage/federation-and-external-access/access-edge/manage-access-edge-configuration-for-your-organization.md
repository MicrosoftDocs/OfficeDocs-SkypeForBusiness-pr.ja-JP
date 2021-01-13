---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを介した会議への外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、および匿名ユーザー アクセスの種類を有効にする必要があります。
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817337"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>組織のアクセス エッジ構成の管理

1 つ以上のエッジ サーバーを展開した後、組織でサポートされるエッジ サーバーを介した会議への外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、および匿名ユーザー アクセスの種類を有効にする必要があります。

こうしたオプションには、[**アクセス エッジ構成**] ページで構成できる次の種類のアクセスが含まれます。

  - **フェデレーションとパブリック IM 接続を有効にする**   フェデレーション パートナー ドメインへのユーザー アクセスをサポートする場合は、これを有効にしてください。 この設定は、[外部アクセス ポリシー] ページでグローバル スコープ、サイト スコープ、またはユーザー スコープ用に構成された SIP フェデレーション **に適用** されます。 フェデレーション設定を適用するには、両方のページでフェデレーション サポートを構成する必要があります。
    
    フェデレーション パートナーの検出方法に関するオプションの設定と、アーカイブについての免責事項 (展開でアーカイブが有効で通信の詳細がアーカイブされるフェデレーション連絡先への通知) を連絡先に送信するかどうかの 2 つのオプションがあります。
    
      - **パートナー ドメインの検出を有効にする**   このオプションを選択すると、フェデレーションを行えるドメインの自動検出が有効になります。 Skype for Business Server は、ドメイン ネーム システム (DNS) レコードを使用して、許可されたドメインの一覧に記載されていないドメインの検出を試み、検出されたフェデレーション パートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、および管理者設定に基づいてトラフィックを制限またはブロックします。 このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。 このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。 詳細については、「許可された [外部ドメインのサポートを構成する」を参照してください](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **フェデレーション パートナーにアーカイブ免責事項を送信する**   このオプションを選択すると、通信の詳細が記録されるという通知を受け取ったフェデレーション パートナーにアーカイブについての免責事項メッセージを送信できます。 フェデレーション パートナー ドメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされているという警告をパートナーに表示する必要があります。 アーカイブの詳細については、「フェデレーション パートナーへのアーカイブについての免責事項の送信を [有効または無効にする」を参照してください](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **リモート ユーザー アクセスを有効にする**   在宅勤務者や出張中のユーザーなど、ファイアウォールの外側に位置する組織内のユーザーが Skype for Business Server に接続する場合は、このオプションを有効にします。 詳細については、「リモート ユーザー [アクセスを有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。

  - **匿名ユーザーが会議にアクセスできる**   内部ユーザーが組織する会議に外部の匿名ユーザーを招待する場合は、このオプションを有効にします。 この設定を有効にすると、匿名ユーザーは会議にのみ使用できます。

> [!NOTE]  
> 外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。 外部ユーザー アクセスのポリシーの作成、構成、適用の詳細については、「組織の外部アクセス ポリシーの管理」 [を参照してください](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**次のコマンドレットを使用してアクセス エッジWindows PowerShell表示する**

  - アクセス エッジ構成情報は、このコマンドレットと **Get-CsAccessEdgeConfiguration** Windows PowerShell使用して表示できます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 
    
    すべてのアクセス エッジ構成設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
     `Get-CsAccessEdgeConfiguration`
    
    次のような情報が表示されます。
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

