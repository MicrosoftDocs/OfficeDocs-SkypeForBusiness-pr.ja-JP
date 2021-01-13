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
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817427"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Skype for Business Server でフェデレーション パートナーの検出を有効または無効にする

エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。 このトピックの手順を使用して、この構成を変更します。

> [!NOTE]  
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。 フェデレーションを有効にする方法の詳細については、「リモート ユーザー アクセスを [有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>組織に対してフェデレーション ドメインの自動検出を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、[**フェデレーション ユーザーとの通信を有効にする**] の [**パートナー ドメインの検出を有効にする**] チェック ボックスをオンまたはオフにして、パートナー ドメインの自動検出を有効また無効にします。

6.  [**確定**] をクリックします。

フェデレーション ユーザーが Skype for Business Server 展開のユーザーと共同作業を行うのを有効にするには、フェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーも構成する必要があります。 詳細については、「フェデレーションと [パブリック IM 接続を有効または無効にする」を参照してください](enable-or-disable-federation-and-public-im-connectivity.md)。 特定のフェデレーション ドメインのアクセス制御の詳細については、「SIP フェデレーション ドメインの管理」および [「SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) フェデレーション プロバイダー [の管理」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>フェデレーション コマンドレットを使用してフェデレーション パートナーの検出Windows PowerShellまたは無効にする

フェデレーション パートナーの検出は、フェデレーション コマンドレットと Windows PowerShell使用してSet-CsAccessEdgeConfigurationできます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 


## <a name="to-enable-discovery-of-federation-partners"></a>フェデレーション パートナーの検出を有効にするには

  - フェデレーション パートナーの検出を有効にするには **、EnablePartnerDiscovery** プロパティの値を True ($True) に設定します。 このプロパティ値を変更するには、DNS SRV ルーティングを有効にする必要があります。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>フェデレーション パートナーの検出を無効にするには

  - フェデレーション パートナーの検出を無効にするには **、EnablePartnerDiscovery** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

