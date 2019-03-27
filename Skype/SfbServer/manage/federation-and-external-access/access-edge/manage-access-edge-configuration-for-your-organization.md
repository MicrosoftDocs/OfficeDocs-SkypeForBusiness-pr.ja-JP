---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 1 つまたは複数のエッジ サーバーを展開するには後に、、外部ドメインまたはプロバイダーのアクセス、リモート ユーザー アクセス、および会議を組織でサポートされるエッジ トランスポート サーバーに匿名ユーザー アクセスの種類を有効にする必要があります。
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896918"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>組織のアクセス エッジ構成の管理

1 つまたは複数のエッジ サーバーを展開するには後に、、外部ドメインまたはプロバイダーのアクセス、リモート ユーザー アクセス、および会議を組織でサポートされるエッジ トランスポート サーバーに匿名ユーザー アクセスの種類を有効にする必要があります。

これらのオプションには、次の種類の**アクセス エッジの構成**] ページで構成可能なアクセスがあります。

  - **フェデレーションとパブリック IM 接続を有効にする**   、フェデレーション パートナーのドメインへのユーザー アクセスをサポートする場合にこれを有効にします。 この設定は、SIP に適用されます、グローバル、サイトのフェデレーションを構成またはユーザー スコープの**外部アクセス ポリシー**のページです。 フェデレーションの設定を適用する、両方のページでフェデレーション サポートを構成する必要があります。
    
    2 つのオプションで存在するのオプションの設定方法、フェデレーション パートナーを検出すると、免責事項をアーカイブするかどうか (フェデレーションの連絡先に通知すると通信できることを展開には有効なアーカイブとの通信詳細はアーカイブされる) の連絡先に送信されます。
    
      - **パートナー ドメインの検出を有効にする**   とフェデレーションを行うことができるドメインの自動検出を有効にこのオプションを選択します。 Skype ビジネス サーバーのドメイン ネーム システム (DNS) レコードを使用して自動的に検出されたフェデレーション パートナーからの着信トラフィックを評価することを制限することや信頼関係に基づいてトラフィックをブロック、許可されるドメインの一覧に表示されていないドメインを探索しようレベル、トラフィック、および管理者設定の量です。 このオプションをオフにすると、フェデレーション ユーザーのアクセスは許可するドメイン] ボックスの一覧に含まれているドメインのユーザーに対してのみ有効です。 このオプションを選択するかどうかは、その個人を指定することをブロックまたは許可されているドメイン フェデレーション ドメインのアクセス エッジ サービスを実行して特定のサーバーにアクセスを制限することです。 詳細については、[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)を参照してください。
    
      - **フェデレーション パートナーへのアーカイブ免責事項を送信**   このオプションを選択するには、通信の詳細が記録されていることが示されますが、フェデレーション パートナーにアーカイブについての免責事項メッセージの送信が有効にします。 フェデレーション パートナーのドメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項パートナーに通知、展開でのメッセージとの通信の詳細をバックアップしていますが有効にする必要があります。 アーカイブの詳細については、[有効にするかフェデレーション パートナーに、アーカイブの免責事項の送信を無効にする](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)を参照してください。

  - **リモート ユーザー アクセスを有効にする**   在宅勤務者、出張中には、Skype のビジネス サーバーに接続できるユーザーなど、ファイアウォールの外側には、組織内のユーザーの場合、このオプションを有効にします。 詳細については、[有効にするかリモート ユーザー アクセスを無効にする](enable-or-disable-remote-user-access.md)を参照してください。

  - **会議にアクセスする匿名ユーザーを有効にする**   内部のユーザーが開催する会議に外部の匿名ユーザーを招待する場合にこのオプションを有効にします。 この設定を有効にするだけでは、匿名ユーザー会議。

> [!NOTE]  
> 外部ユーザー アクセスを有効にするだけでなくサポート、また任意の種類の外部ユーザー アクセスのユーザーが利用できる前に、組織内のリモート ユーザー アクセスの使用を制御するポリシーを構成します。 作成、構成、および外部ユーザー アクセスのポリシーの適用に関する詳細については、[組織の外部アクセス ポリシーの管理](../external-access-policies/manage-external-access-policy-for-your-organization.md)を参照してください。

**Windows PowerShell コマンドレットを使用して、アクセス エッジの構成情報を表示します。**

  - Windows PowerShell と**Get CsAccessEdgeConfiguration**コマンドレットを使用して、アクセス エッジの構成情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 
    
    すべてのアクセス エッジ構成設定に関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。
    
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

