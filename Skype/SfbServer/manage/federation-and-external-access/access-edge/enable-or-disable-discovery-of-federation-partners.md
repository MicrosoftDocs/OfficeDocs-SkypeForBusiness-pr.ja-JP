---
title: フェデレーション パートナーの検出の有効化または無効化
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 時に、エッジ サーバーの展開し、フェデレーションを有効になっている、組織の必要がある指定したフェデレーション パートナー ドメインの自動検出をサポートするかどうか。
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199942"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>有効にするか、ビジネスのサーバーの Skype でのフェデレーション パートナーの検出を無効にします。

時に、エッジ サーバーの展開し、フェデレーションを有効になっている、組織の必要がある指定したフェデレーション パートナー ドメインの自動検出をサポートするかどうか。 その構成を変更するのにはこのトピックの手順を使用します。

> [!NOTE]  
> 次の手順では、組織のフェデレーションが既に有効にことを前提としています。 フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](enable-or-disable-remote-user-access.md)を参照してください。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>有効にするか、組織のフェデレーション ドメインの自動検出を無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3.  左側のナビゲーション ・ バーで [**外部ユーザー アクセス**] をクリックして、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。

5.  **アクセス エッジ構成の編集**、**フェデレーション ユーザーとの通信を有効にする**には、選択またはを有効にするか、パートナー ドメインの自動検出を無効にするには、**パートナー ドメインの検出を有効にする**] チェック ボックスをオフにします。

6.  [**コミット**] をクリックします。

フェデレーション ユーザーにビジネスのサーバーの展開に、Skype のユーザーと共同作業を有効にするには、必要がありますもしているフェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーです。 詳細については、[有効にするかフェデレーションとパブリック IM 接続を無効にする](enable-or-disable-federation-and-public-im-connectivity.md)を参照してください。 特定のフェデレーション ドメインのアクセスを制御する方法の詳細は、[ドメインをフェデレーションする SIP を管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)し、[プロバイダーをフェデレーションする SIP の管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)を参照してください。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>有効にするか、Windows PowerShell コマンドレットを使用してフェデレーション パートナーの検出を無効にします。

フェデレーション パートナーの検出は、Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 


## <a name="to-enable-discovery-of-federation-partners"></a>フェデレーション パートナーの検出を有効にするには

  - フェデレーション パートナーの検出を有効にするには、 **EnablePartnerDiscovery**プロパティの値を True ($True) に設定します。 DNS SRV がこのプロパティの値を変更するのにはルーティングを有効にする必要があることに注意してください。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>フェデレーション パートナーの検出を無効にするには

  - フェデレーション パートナーの検出を無効にするには、 **EnablePartnerDiscovery**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

