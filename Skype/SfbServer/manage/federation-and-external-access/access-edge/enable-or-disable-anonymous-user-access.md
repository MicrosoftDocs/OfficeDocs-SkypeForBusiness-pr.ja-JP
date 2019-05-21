---
title: 匿名ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280272"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Skype for Business Server で匿名ユーザーのアクセスを有効または無効にする

匿名ユーザーは、組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインでユーザーアカウントを持っていないユーザーですが、オンプレミスの会議にリモートで参加するよう招待することができます。 会議への匿名参加を許可することにより、匿名ユーザーを有効にします (つまり、会議または会議キーによって id が確認されたユーザーのみ)、会議に参加できます。 匿名での参加を許可するには、組織で匿名参加を有効にする必要があります。

匿名ユーザーによるアクセスを一時的または完全に回避する必要がある場合は、組織で無効にすることができます。 このセクションの手順を使用して、組織の匿名ユーザーアクセスを有効または無効にします。

> [!NOTE]  
> 組織に対して匿名ユーザーアクセスを有効にすると、アクセスエッジサービスを実行しているサーバーでは、匿名ユーザーによるアクセスがサポートされることを指定するだけです。 匿名ユーザーは、少なくとも1つの会議ポリシーを構成し、1つ以上のユーザーまたはユーザーグループに適用するまで、組織内のすべての会議に参加することはできません。 匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成されている会議ポリシーが割り当てられているユーザーのみです。 匿名ユーザーの招待をサポートするように会議ポリシーを構成する方法について詳しくは、「[会議ポリシーを管理](../../conferencing/conferencing-policies.md)する」をご覧ください。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>組織の匿名ユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織の匿名ユーザーアクセスを有効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - 組織の匿名ユーザーアクセスを無効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオフにします。

6.  [**コミット**] をクリックします。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して匿名ユーザーのアクセスを有効または無効にする

Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して、匿名ユーザーのアクセスを管理できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 

## <a name="to-enable-anonymous-user-access"></a>匿名ユーザーのアクセスを有効にするには

  - 匿名ユーザーのアクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>匿名ユーザーのアクセスを無効にするには

  - 匿名ユーザーのアクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>関連項目

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
