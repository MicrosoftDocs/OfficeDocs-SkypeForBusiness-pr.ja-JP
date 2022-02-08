---
title: 匿名ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 匿名ユーザー アクセスを有効または無効にする方法は、Skype for Business Server。
ms.openlocfilehash: 382bc8bcbfce478677264a6a6da2e791a05b945e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395329"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>ユーザーの匿名ユーザー アクセスを有効または無効Skype for Business Server

匿名ユーザーとは、組織の Active Directory ドメイン サービスまたはサポートされているフェデレーション ドメインにユーザー アカウントを持たないが、オンプレミスの会議にリモートから参加するために招待できるユーザーです。 会議への匿名参加を許可すると、匿名ユーザー (つまり、会議または会議キーを通じて ID が確認されるユーザー) が会議に参加できます。 匿名参加を許可するには、組織で有効にする必要があります。

後で匿名ユーザーによるアクセスを一時的または完全に防止する場合は、組織で無効にできます。 組織の匿名ユーザー アクセスを有効または無効にするには、このセクションの手順を使用します。

> [!NOTE]  
> 組織で匿名ユーザー アクセスを有効にすることで、Access Edge サービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートする必要があるだけになります。 匿名ユーザーは、少なくとも 1 つの会議ポリシーを構成し、1 つ以上のユーザーまたはユーザー グループに適用するまで、組織内の会議に参加できません。 匿名ユーザーを会議に招待できる唯一のユーザーは、匿名ユーザーをサポートするように構成された会議ポリシーが割り当てられているユーザーです。 匿名ユーザーの招待をサポートするための会議ポリシーの構成の詳細については、「会議ポリシーの管理 [」を参照してください](../../conferencing/conferencing-policies.md)。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>組織の匿名ユーザー アクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織で匿名ユーザー アクセスを有効にするには、[匿名ユーザーとの通信を有効にする **] チェック ボックス** をオンにします。
    
      - 組織の匿名ユーザー アクセスを無効にするには、[匿名ユーザーとの通信を有効にする **] チェック ボックスを** オフにします。

6.  [**確定**] をクリックします。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用して匿名ユーザー アクセスを有効またはWindows PowerShellする

匿名ユーザー アクセスを管理するには、Windows PowerShell **Set-CsAccessEdgeConfiguration コマンドレットを使用** します。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 

## <a name="to-enable-anonymous-user-access"></a>匿名ユーザー アクセスを有効にするには

  - 匿名ユーザー アクセスを有効にするには、 **AllowAnonymousUsers** プロパティの値を True ($True) に設定します。<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>匿名ユーザー アクセスを無効にするには

  - 匿名ユーザー アクセスを無効にするには、 **AllowAnonymousUsers** プロパティの値を False ($False) に設定します。<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>関連項目

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
