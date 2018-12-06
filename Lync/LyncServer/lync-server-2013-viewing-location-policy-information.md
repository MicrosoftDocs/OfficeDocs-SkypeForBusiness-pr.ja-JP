---
title: 場所ポリシー情報の表示
TOCTitle: 場所ポリシー情報の表示
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48271355
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 場所ポリシー情報の表示

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 では、場所ポリシーを使用して、Enhanced 9-1-1 (E9-1-1) 機能とユーザーまたは連絡先の場所の設定に関連する設定を適用します。場所ポリシーには、ユーザーを E9-1-1 に対して有効にするかどうか、および有効にする場合、緊急電話の動作を指定します。たとえば、場所ポリシーを使用して、緊急電話の番号 (米国の場合は 911)、社内セキュリティに自動的に通知するかどうか、および通話をルーティングする方法を定義できます。

場所ポリシーは、Lync Server 2013 コントロール パネルの \[**ネットワーク構成**\] グループから構成できます。また、このポリシーは、Lync Server コントロール パネルで、表示、作成、変更、または削除できます。場所ポリシーに関する情報を表示するには次の手順を使用します。場所ポリシーの作成と変更の詳細については、「[場所ポリシーの作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)」を参照してください。

## 場所ポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**場所のポリシー**\] をクリックします。

4.  \[**場所のポリシー**\] ページで、変更する場所のポリシーを選択します。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。
    
    > [!NOTE]
    > 同時に表示できるのは 1 つの場所ポリシーのみです。


「グローバル」という名前の単一ポリシーが、既定で存在します。このポリシーは、削除することも名前を変更することもできません。 ただし、グローバル ポリシーの内容を変更することはできます。 このポリシーは、サイト ポリシーまたはユーザー単位のポリシーが作成されていない場合に限り、すべてのユーザーおよび連絡先に適用されます。 ユーザー単位のポリシーは、特定のユーザーに適用する必要があります。

## 関連項目

#### タスク

[場所ポリシーの作成または変更](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[場所ポリシーの作成](lync-server-2013-create-location-policies.md)  
[Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)  

#### その他のリソース

[New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsLocationPolicy)

