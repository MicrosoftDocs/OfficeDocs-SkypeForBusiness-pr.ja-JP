---
title: フェデレーション パートナーの検出の有効化または無効化
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: エッジサーバーを展開して組織のフェデレーションを有効にした時点で、フェデレーションパートナードメインの自動検出をサポートするかどうかを指定する必要があります。
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280258"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Skype for Business Server でフェデレーションパートナーの検出を有効または無効にする

エッジサーバーを展開して組織のフェデレーションを有効にした時点で、フェデレーションパートナードメインの自動検出をサポートするかどうかを指定する必要があります。 この設定を変更するには、このトピックの手順を使用します。

> [!NOTE]  
> 次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。 フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](enable-or-disable-remote-user-access.md)にする」をご覧ください。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>組織のフェデレーションドメインの自動検出を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、パートナードメインの自動検出を有効または無効にするには、[**パートナードメインの検出を有効**にする] チェックボックスをオンまたはオフにします。

6.  [**コミット**] をクリックします。

フェデレーションされたユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成しておく必要があります。 詳細について[は、「フェデレーションとパブリック IM 接続を有効または無効](enable-or-disable-federation-and-public-im-connectivity.md)にする」を参照してください。 特定のフェデレーションドメインのアクセス制御について詳しくは、「 [sip フェデレーションドメインを管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)する」と「 [sip フェデレーションプロバイダーを管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)する」をご覧ください。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、フェデレーションパートナーの検出を有効または無効にする

フェデレーションパートナーの検出は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 


## <a name="to-enable-discovery-of-federation-partners"></a>フェデレーションパートナーの検出を有効にするには

  - フェデレーションパートナーの検出を有効にするには、 **Enablepartnerdiscovery**プロパティの値を True ($True) に設定します。 このプロパティ値を変更するには、DNS SRV ルーティングを有効にする必要があることに注意してください。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>フェデレーションパートナーの検出を無効にするには

  - フェデレーションパートナーの検出を無効にするには、 **Enablepartnerdiscovery**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

