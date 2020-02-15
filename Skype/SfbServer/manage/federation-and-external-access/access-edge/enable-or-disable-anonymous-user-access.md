---
title: 匿名ユーザーアクセスを有効または無効にする
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006002"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Skype for Business Server で匿名ユーザーアクセスを有効または無効にする

匿名ユーザーは、組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインにユーザーアカウントを持たないユーザーですが、社内の会議にリモートで参加するよう招待することができます。 会議への匿名参加を許可することにより、匿名ユーザー (つまり、会議キーまたは会議キーで本人のみが確認されるユーザー) が会議に参加できるようになります。 匿名参加を許可するには、組織に対して有効にする必要があります。

後で匿名ユーザーによるアクセスを一時的または完全に禁止する場合は、組織に対して無効にすることができます。 このセクションの手順を使用して、組織の匿名ユーザーアクセスを有効または無効にします。

> [!NOTE]  
> 組織で匿名ユーザーアクセスを有効にすることで、アクセスエッジサービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートすることを指定するだけです。 匿名ユーザーは、少なくとも1つの会議ポリシーを構成して、1人以上のユーザーまたはユーザーグループに適用するまでは、組織内のすべての会議に参加できません。 匿名ユーザーを会議に招待できるユーザーは、匿名ユーザーをサポートするように構成された会議ポリシーが割り当てられているユーザーのみです。 匿名ユーザーの招待をサポートするための会議ポリシーの構成の詳細については、「 [Manage a コンファレンス policies](../../conferencing/conferencing-policies.md)」を参照してください。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>組織の匿名ユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織で匿名ユーザーアクセスを有効にするには、[**匿名ユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - 組織の匿名ユーザーアクセスを無効にするには、[**匿名ユーザーとの通信を有効に**する] チェックボックスをオフにします。

6.  [**確定**] をクリックします。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して匿名ユーザーアクセスを有効または無効にする

匿名ユーザーアクセスを管理するには、Windows PowerShell と**set-csaccessedgeconfiguration**コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-enable-anonymous-user-access"></a>匿名ユーザーアクセスを有効にするには

  - 匿名ユーザーアクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>匿名ユーザーアクセスを無効にするには

  - 匿名ユーザーアクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>関連項目

[設定-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
