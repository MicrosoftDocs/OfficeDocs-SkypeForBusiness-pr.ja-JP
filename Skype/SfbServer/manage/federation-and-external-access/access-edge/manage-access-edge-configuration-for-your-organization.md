---
title: 組織のアクセス エッジ構成の管理
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 1つ以上のエッジサーバーを展開した後、組織でサポートされているエッジサーバー経由での会議への外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、匿名ユーザーアクセスの種類を有効にする必要があります。
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280195"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>組織のアクセス エッジ構成の管理

1つ以上のエッジサーバーを展開した後、組織でサポートされているエッジサーバー経由での会議への外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、匿名ユーザーアクセスの種類を有効にする必要があります。

これらのオプションには、[**アクセスエッジ構成**] ページから構成できる次の種類のアクセスがあります。

  - **フェデレーションとパブリック IM 接続**   を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、この機能を有効にします。 この設定は、[**外部アクセスポリシー** ] ページのグローバル、サイト、またはユーザーのスコープ用に構成された SIP フェデレーションに適用されます。 フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。
    
    フェデレーションパートナーの検出方法に関するオプションの設定である2つのオプションと、アーカイブの免責事項 (展開によって通信するフェデレーションされた連絡先に通知します。詳細がアーカイブされます) がコンタクトに送信されます。
    
      - **[パートナードメインの検出**   を有効にする] このオプションをオンにすると、フェデレーションできるドメインの自動検出が有効になります。 Skype for Business Server では、ドメインネームシステム (DNS) レコードを使って、[許可したドメイン] 一覧にないドメインを検出し、検出されたフェデレーションパートナーから受信トラフィックを自動的に評価し、信頼関係に基づいてそのトラフィックを制限またはブロックします。レベル、トラフィックの量、管理者の設定。 このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。 このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。 詳細については、「[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)」を参照してください。
    
      - **[アーカイブに関する免責事項をフェデレーションパートナー**   に送信する] このオプションをオンにすると、フェデレーションパートナーにアーカイブの免責事項メッセージを送信し、通信の詳細が記録されることを通知します。 フェデレーションパートナードメインとの外部通信をアーカイブする場合は、アーカイブの免責事項の通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。 アーカイブの詳細については、「[フェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」を参照してください。

  - **[リモートユーザーアクセス**   を有効にする] このオプションは、出張中の在宅勤務者やユーザーなど、組織内のユーザーが Skype for business Server に接続できるようにする場合に有効にします。 詳細について[は、「リモートユーザーアクセスを有効または無効](enable-or-disable-remote-user-access.md)にする」を参照してください。

  - **[匿名ユーザーが会議**   にアクセスできるようにする] このオプションを有効にすると、内部ユーザーが、自分が開催する会議に外部匿名ユーザーを招待することができます。 この設定を有効にすると、会議の匿名ユーザーのみを許可します。

> [!NOTE]  
> 外部ユーザーアクセスのサポートを有効にするだけでなく、組織でのリモートユーザーアクセスの使用を制御するポリシーも構成して、ユーザーが外部ユーザーアクセスの種類を利用できるようにする必要があります。 外部ユーザーアクセスのポリシーの作成、構成、適用の詳細については、「[組織の外部アクセスポリシーを管理](../external-access-policies/manage-external-access-policy-for-your-organization.md)する」を参照してください。

**Windows PowerShell コマンドレットを使用してアクセスエッジ構成情報を表示する**

  - Access Edge の構成情報は、Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 
    
    すべてのアクセスエッジの構成設定に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
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

