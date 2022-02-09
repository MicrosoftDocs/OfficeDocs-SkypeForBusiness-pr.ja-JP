---
title: 匿名ユーザーをサポートする会議ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: 匿名ユーザーをサポートするよう会議ポリシーを構成し、この会議ポリシーを特定のユーザーに適用することで、匿名ユーザーを招待できるユーザーを制御します。
ms.openlocfilehash: 31978a997b3344367068c00978de9257585c6d4b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399711"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>会議ポリシーを割り当て、ユーザーの匿名ユーザーをサポートSkype for Business Server 


既定では、どのユーザーも匿名ユーザーを会議に招待することはできません。 匿名ユーザーをサポートするよう会議ポリシーを構成し、この会議ポリシーを特定のユーザーに適用することで、匿名ユーザーを招待できるユーザーを制御します。 匿名ユーザーをサポートする会議ポリシーを構成する方法の詳細については、「Skype for Business Server での会議ポリシーの作成」および[「フェデレーション](../../conferencing/create-policies.md)の管理」および「Skype for Business Server への外部アクセス」[を参照してください](../managing-federation-and-external-access.md)。

このセクションの手順を使用して、既に作成した会議ポリシーを、1 人以上のユーザーまたは 1 つ以上のユーザー グループに適用します。

> [!NOTE]  
> ユーザーが匿名ユーザーを招待できるようにするポリシーを構成して適用するほかに、組織の匿名ユーザーのサポートを有効にする必要もあります。 詳細については、「Configure [policis to control public user](../external-access-policies/configure-policies-to-control-public-user-access.md) access in Skype for Business Server。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>会議への匿名参加に対するユーザー ポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで [**会議**] をクリックし、次のどちらかの操作を行います。
    
    1.  新しいユーザー ポリシーを作成するには、[**新規作成**] をクリックし、[**ユーザー ポリシー**] をクリックします。 [**名前**] フィールドに、ユーザー ポリシーの範囲を示す一意の名前を作成します (匿名ユーザーとの通信を有効にするユーザー ポリシーの場合は **EnableAnonymous** など)。
    
    2.  既存のユーザー ポリシーを編集する場合は、表の一覧にある適切なポリシーをクリックして [**編集**] をクリックし、[**詳細の表示**] をクリックします。

4.  [**会議ポリシー**] ダイアログ ボックスの [**参加者に匿名ユーザーの招待を許可する**] チェック ボックスをオンにします。

5.  [**確定**] をクリックします。

6.  左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。

7.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

8.  [**会議ポリシー Skype for Business Server** ユーザーの編集] で、このユーザーに適用する匿名ユーザー アクセス構成を持つユーザー ポリシーを選択します。  

    > [!NOTE]  
    > 自動 <STRONG>&lt;設定&gt;</STRONG> は、既定のサーバー インストール設定を適用し、サーバーによって自動的に適用されます。


ユーザーが匿名ユーザーを会議に招待できるようにするには、組織で匿名ユーザーのサポートも有効にしておく必要があります。 詳細については、「Configure [policis to control public user](../external-access-policies/configure-policies-to-control-public-user-access.md) access in Skype for Business Server。

