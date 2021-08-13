---
title: フェデレーション パートナーの検出の有効化または無効化
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。
ms.openlocfilehash: 4877472ca48f5fc6dc166f5f4cbcab8b7441d7ff8eb3a0f8c5b914242da686ff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297233"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>フェデレーション パートナーの検出を有効または無効にするSkype for Business Server

エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。 このトピックの手順を使用して、この構成を変更します。

> [!NOTE]  
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。 フェデレーションの有効化の詳細については、「リモート ユーザー アクセス [を有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>組織に対してフェデレーション ドメインの自動検出を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、[**フェデレーション ユーザーとの通信を有効にする**] の [**パートナー ドメインの検出を有効にする**] チェック ボックスをオンまたはオフにして、パートナー ドメインの自動検出を有効また無効にします。

6.  [**確定**] をクリックします。

フェデレーション ユーザーが Skype for Business Server 展開でユーザーと共同作業を行う場合は、フェデレーション ユーザー アクセスをサポートするように少なくとも 1 つの外部アクセス ポリシーも構成している必要があります。 詳細については、「フェデレーションと [パブリック IM 接続を有効または無効にする」を参照してください](enable-or-disable-federation-and-public-im-connectivity.md)。 特定のフェデレーション ドメインのアクセス制御の詳細については [、「MANAGE SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) フェデレーション ドメイン」および [「MANAGE SIP フェデレーション プロバイダー」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>フェデレーション パートナーの検出を有効または無効にする場合は、Windows PowerShellコマンドレットを使用します。

フェデレーション パートナーの検出は、フェデレーション パートナーとWindows PowerShellコマンドレットをSet-CsAccessEdgeConfigurationできます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 


## <a name="to-enable-discovery-of-federation-partners"></a>フェデレーション パートナーの検出を有効にするには

  - フェデレーション パートナーの検出を有効にするには **、EnablePartnerDiscovery** プロパティの値を True ($True) に設定します。 このプロパティ値を変更するには、DNS SRV ルーティングを有効にする必要があります。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>フェデレーション パートナーの検出を無効にするには

  - フェデレーション パートナーの検出を無効にするには **、EnablePartnerDiscovery** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

