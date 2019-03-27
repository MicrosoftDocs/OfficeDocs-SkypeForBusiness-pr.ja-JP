---
title: 匿名ユーザー サポートのための会議ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーを制御、匿名ユーザーをサポートするための会議ポリシーを構成して、特定のユーザーにその会議のポリシーを適用することによって匿名ユーザーを招待することができます。
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881128"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Skype のビジネス サーバーの匿名ユーザーをサポートする会議ポリシーを割り当てください。 


既定では、すべてのユーザーが会議に参加する匿名ユーザーの招待からできませんでした。 ユーザーを制御、匿名ユーザーをサポートするための会議ポリシーを構成して、特定のユーザーにその会議のポリシーを適用することによって匿名ユーザーを招待することができます。 匿名ユーザーをサポートするための会議ポリシーを構成する方法の詳細については、 [Skype ビジネス サーバー用の会議ポリシーを作成する](../../conferencing/create-policies.md)」および「[フェデレーションの管理および業務サーバー Skype への外部アクセス](../managing-federation-and-external-access.md)を参照してください。

このセクションの 1 つまたは複数のユーザーまたはユーザー グループを既に作成した会議ポリシーを適用するのに手順を使用します。

> [!NOTE]  
> 構成して匿名ユーザーを招待するユーザーを有効にするポリシーを適用するだけでなくも、組織の匿名ユーザーのサポートを有効にする必要があります。 詳細については、 [Skype のビジネス サーバーのパブリック ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)を参照してください。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>会議への匿名参加に対するユーザー ポリシーを構成するのには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**会議**をクリックし、次のいずれかの操作を行います。
    
    1.  新しいユーザー ポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザー ポリシー**] をクリックします。 ユーザー ポリシーの説明 (たとえば、匿名ユーザーとの通信を有効にするユーザー ポリシーの**EnableAnonymous** ) を示す**名前**」フィールドに一意の名前を作成します。
    
    2.  既存のユーザー ポリシーを構成するのには、表に記載されている適切なポリシー] をクリック**を編集**するには、**の詳細を表示**] をクリックします。

4.  **会議ポリシー** ] ダイアログ ボックスで、[**匿名ユーザーを招待する参加者を許可する**] チェック ボックスを選択します。

5.  [**コミット**] をクリックします。

6.  左側のナビゲーション バーで [**ユーザー**] をクリックしてを構成するユーザー アカウントを検索します。

7.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

8.  **ビジネス サーバー ユーザーの編集の Skype**の**会議**ポリシーでは、このユーザーに適用する匿名ユーザー アクセスの構成とユーザー ポリシーを選択します。  

    > [!NOTE]  
    > <STRONG>&lt;自動&gt;</STRONG>の設定はサーバー インストールの既定の設定を適用し、サーバーによって自動的に適用されます。


会議への匿名ユーザーを招待するユーザーを有効にするも、組織で匿名ユーザーのサポートを有効にする必要があります。 詳細については、 [Skype のビジネス サーバーのパブリック ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)を参照してください。

