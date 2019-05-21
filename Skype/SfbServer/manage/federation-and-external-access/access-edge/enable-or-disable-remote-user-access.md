---
title: リモート ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: リモートユーザーに対してリモートユーザーアクセスを有効にすると、サポートされているリモートユーザーはインターネット経由で接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280237"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Skype for Business Server のリモートユーザーアクセスを有効または無効にする

リモートユーザーは組織内のユーザーで、組織内に Active Directory id が固定されています。 リモートユーザーは、組織のネットワークに接続されていないときに仮想プライベートネットワーク (VPN) を使用して、ネットワークの外部から Skype for Business Server にサインインすることがよくあります。 リモートユーザーには、自宅や外出先で作業している従業員や、信頼できるベンダーなど、企業の資格情報が付与されている信頼できる社員が含まれます。 リモートユーザーに対してリモートユーザーアクセスを有効にすると、サポートされているリモートユーザーはインターネット経由で接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。

リモートユーザーアクセスをサポートするには、リモートユーザーアクセスを有効にする必要があります。 リモートユーザーアクセスを有効にすると、組織全体で有効にすることができます。 後でリモートユーザーのアクセスを一時的または完全に禁止する必要がある場合は、組織に対して無効にすることができます。 組織のリモートユーザーアクセスを有効または無効にするには、このセクションの手順を使用します。


> [!NOTE]  
> リモートユーザーアクセスを有効にすることは、アクセスエッジサービスを実行しているサーバーがリモートユーザーとの通信をサポートしていることを示しますが、リモートユーザーは、を構成するまで、組織内のインスタントメッセージング (IM) または会議に参加することはできません。リモートユーザーアクセスの使用を管理するためのポリシーが少なくとも1つあります。 1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 リモートユーザーアクセスを使用するためのポリシーの構成の詳細については、「 [Skype For Business Server でリモートユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)」を参照してください。


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>組織のリモートユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織のリモートユーザーアクセスを有効にするには、[**リモートユーザーアクセスを有効**にする] チェックボックスをオンにします。
    
      - 組織のリモートユーザーアクセスを無効にするには、[**リモートユーザーアクセスを有効に**する] チェックボックスをオフにします。

6.  [**コミット**] をクリックします。

リモートユーザーが Skype for Business Server を実行しているサーバーにサインインできるようにするには、リモートユーザーのアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳細については、「 [Skype For Business Server でリモートユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)」を参照してください。


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したリモートユーザーアクセスの有効化または無効化

リモートユーザーアクセスを管理するには、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-enable-remote-user-access"></a>リモートユーザーアクセスを有効にするには

  - リモートユーザーアクセスを有効にするには、 **Allowoutsideusers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>リモートユーザーアクセスを無効にするには

  - リモートユーザーアクセスを無効にするには、 **Allowoutsideusers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


