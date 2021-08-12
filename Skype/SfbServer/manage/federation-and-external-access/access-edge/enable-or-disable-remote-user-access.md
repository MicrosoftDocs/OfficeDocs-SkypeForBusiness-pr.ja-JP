---
title: リモート ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: リモート ユーザーに対してリモート ユーザー アクセスを有効にした場合、サポートされているリモート ユーザーはインターネットを使用して接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。
ms.openlocfilehash: 3b95796efbd8056092a24399f6faa7ccd3619b7168a2bb787436beeb3f78f4fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313185"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>リモート ユーザー アクセスを有効または無効にする方法は、Skype for Business Server

リモート ユーザーは、組織内の永続的な Active Directory ID を持つ、組織内のユーザーです。 リモート ユーザーは、組織Skype for Business Server接続されていない仮想プライベート ネットワーク (VPN) を使用して、ネットワークの外部からユーザーにサインインする場合が多い。 リモート ユーザーには自宅や外出先で作業する従業員のほか、エンタープライズ資格情報を付与された信頼できるベンダーなどのリモート作業者が含まれます。 リモート ユーザーに対してリモート ユーザー アクセスを有効にした場合、サポートされているリモート ユーザーはインターネットを使用して接続し、Skype for Business Server を使用して内部ユーザーと共同作業するために VPN を使用して接続する必要はありません。

リモート ユーザー アクセスをサポートするには、リモート ユーザー アクセスを有効にする必要があります。有効にする場合は、組織全体に対して有効にします。後でリモート ユーザー アクセスを一時的または永久に禁止する場合は、組織に対するリモート ユーザー アクセスを無効にできます。組織に対するリモート ユーザー アクセスを有効または無効にするには、このセクションの手順を使用します。


> [!NOTE]  
> リモート ユーザー アクセスを有効にした時点では、アクセス エッジ サービスを実行するサーバーがリモート ユーザーとの通信をサポートするという指定が行われるだけです。 Skype for Business Serverレベルで適用されるポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。 Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 リモート ユーザー アクセスを使用するためのポリシーの構成の詳細については、「Configure policis to control remote user access in Skype for Business Server」[を参照してください](../external-access-policies/configure-policies-to-control-remote-user-access.md)。


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>組織に対するリモート ユーザー アクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織に対してリモート ユーザー アクセスを有効にするには、[**リモート ユーザー アクセスを有効にする**] チェック ボックスをオンにします。
    
      - 組織に対してリモート ユーザー アクセスを無効にするには、[**リモート ユーザー アクセスを有効にする**] チェック ボックスをオフにします。

6.  [**確定**] をクリックします。

リモート ユーザーが Skype for Business Server を実行しているサーバーにサインインするには、リモート ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーも構成する必要があります。 詳細については、「Configure [policis to control remote user](../external-access-policies/configure-policies-to-control-remote-user-access.md)access in Skype for Business Server」 を参照してください。


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>リモート ユーザー アクセスを有効または無効にする場合は、Windows PowerShellコマンドレットを使用します。

リモート ユーザー アクセスは、リモート ユーザー アクセスと Windows PowerShellコマンドレットをSet-CsAccessEdgeConfigurationできます。 このコマンドレットは、2013 管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 

## <a name="to-enable-remote-user-access"></a>リモート ユーザー アクセスを有効にするには

  - リモート ユーザー アクセスを有効にするには、**AllowOutsideUsers** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>リモート ユーザー アクセスを無効にするには

  - リモート ユーザー アクセスを無効にするには、**AllowOutsideUsers** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


