---
title: 匿名ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a68790f870a6c62b513caab559580695763cd4df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199949"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>有効にするか、ビジネスのサーバーの Skype の匿名ユーザー アクセスを無効にします。

匿名ユーザーは、ユーザーが組織の Active Directory ドメイン サービスまたはサポートされているフェデレーション ドメインのユーザー アカウントはありませんが、オンプレミス会議にリモートで参加するように招待することができます。 匿名ユーザー (つまり、ユーザー id を確認して会議出席依頼や会議のキーのみを使用) を有効にした匿名ミーティングへの参加を許可することで会議に参加します。 匿名参加を許可するには、組織では有効にする必要があります。

後で、一時的または恒久的には、匿名ユーザーによるアクセスを防ぐためにする場合は、組織に無効にできます。 このセクションでを有効にするか、組織の匿名ユーザー アクセスを無効にする手順を使用します。

> [!NOTE]  
> 組織の匿名ユーザー アクセスを有効にすることによってのみを指定するアクセス エッジ サービスを実行しているサーバーが匿名ユーザーによるアクセスをサポートします。 匿名ユーザーが表示されるまでも、少なくとも 1 つの会議ポリシーを構成する 1 つまたは複数のユーザーまたはユーザー グループに適用する、組織内のすべての会議に参加できません。 匿名ユーザーをサポートするために構成されている会議ポリシーを割り当てられているこれらのユーザーは会議への匿名ユーザーを招待することがあるユーザーだけです。 匿名ユーザーの招待をサポートするための会議ポリシーを構成する方法の詳細は、[会議ポリシーの管理](../../conferencing/conferencing-policies.md)を参照してください。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>有効にするか、組織の匿名ユーザー アクセスを無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**アクセス エッジの構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。

5.  **アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織の匿名ユーザー アクセスを有効にするには、**匿名ユーザーとの通信を有効にする**] チェック ボックスを選択します。
    
      - 組織の匿名ユーザー アクセスを無効にするには、**匿名ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

6.  [**コミット**] をクリックします。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>有効にするか、Windows PowerShell コマンドレットを使用して匿名ユーザーのアクセスを無効にします。

Windows PowerShell と**セット CsAccessEdgeConfiguration**コマンドレットを使用して、匿名ユーザー アクセスを管理できます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 

## <a name="to-enable-anonymous-user-access"></a>匿名ユーザー アクセスを有効にするには

  - 匿名ユーザー アクセスを有効にするには、 **AllowAnonymousUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>匿名ユーザー アクセスを無効にするには

  - 匿名ユーザー アクセスを無効にするには、 **AllowAnonymousUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>関連項目

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
