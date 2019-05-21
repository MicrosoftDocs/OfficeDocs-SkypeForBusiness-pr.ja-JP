---
title: 匿名ユーザー サポートのための会議ポリシーの割り当て
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 匿名ユーザーをサポートする会議ポリシーを構成し、その会議ポリシーを特定のユーザーに適用することによって、匿名ユーザーを招待できるユーザーを制御します。
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280286"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Skype for Business Server で匿名ユーザーをサポートする会議ポリシーを割り当てる 


既定では、すべてのユーザーが匿名ユーザーを招待して会議に参加することはできません。 匿名ユーザーをサポートする会議ポリシーを構成し、その会議ポリシーを特定のユーザーに適用することによって、匿名ユーザーを招待できるユーザーを制御します。 匿名ユーザーをサポートするように会議ポリシーを構成する方法について詳しくは、「 [skype For Business server で会議ポリシーを作成](../../conferencing/create-policies.md)する」と「 [Skype for business server へのフェデレーションと外部アクセスを管理](../managing-federation-and-external-access.md)する」をご覧ください。

このセクションの手順を使用して、既に作成済みの会議ポリシーを1人または複数のユーザーまたはユーザーグループに適用します。

> [!NOTE]  
> ユーザーが匿名ユーザーを招待できるようにポリシーを構成して適用することに加えて、組織の匿名ユーザーのサポートも有効にする必要があります。 詳細については、「 [Skype For Business Server でパブリックユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)」を参照してください。


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>会議への匿名参加用のユーザーポリシーを構成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで、[**会議**] をクリックし、次のいずれかの操作を行います。
    
    1.  新しいユーザーポリシーを作成するには、[**新規**作成] をクリックし、[**ユーザーポリシー**] をクリックします。 [**名前**] フィールドに、ユーザーポリシーがどのようなものであるかを示す一意の名前を作成します (たとえば、匿名ユーザーとの通信を可能にする、ユーザーポリシーに対して**anonymous**を有効にします)。
    
    2.  既存のユーザーポリシーを構成するには、表に記載されている適切なポリシーをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

4.  [**会議ポリシー** ] ダイアログボックスで、[**参加者に匿名ユーザーの招待を許可する**] チェックボックスをオンにします。

5.  [**コミット**] をクリックします。

6.  左側のナビゲーションバーで [**ユーザー**] をクリックし、構成するユーザーアカウントを検索します。

7.  検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

8.  [**会議ポリシー**] の [ **Skype For business Server ユーザーの編集**] で、このユーザーに適用する匿名ユーザーアクセス構成を持つユーザーポリシーを選択します。  

    > [!NOTE]  
    > <STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーインストール設定が適用され、サーバーによって自動的に適用されます。


ユーザーが会議に匿名ユーザーを招待できるようにするには、組織内の匿名ユーザーのサポートも有効にする必要があります。 詳細については、「 [Skype For Business Server でパブリックユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-public-user-access.md)」を参照してください。

