---
title: 'Lync Server 2013: グループ通話ピックアップの容量計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 403a00887cb64b33075f173499e855eb8783bb20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 でのグループ通話ピックアップの処理能力計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-12_

<div id="sectionSection0" class="section">

次の表では、容量計画の要件の基礎として使用できるグループ通話ピックアップユーザーモデルについて説明します。

<div>


> [!IMPORTANT]  
> グループ通話ピックアップは、コールパークアプリケーションに基づいています。 障害復旧の処理能力を計画する場合は、ペアになっているプールの各プールで、両方のプールのグループ通話ピックアップを含むコールパークサービスのワークロードを処理できる必要があることに留意してください。



</div>

### <a name="group-call-pickup-user-model"></a>グループ通話ピックアップユーザーモデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>測定基準</th>
<th>フロントエンドプールごと (8 台のフロントエンドサーバー)</th>
<th>Standard Edition サーバーごと</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>グループあたりの推奨ユーザー数</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>推奨されるグループの数</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>グループ通話ピックアップを有効にしたプールあたりの最大ユーザー数</p></td>
<td><p>25,000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>プールごとに1分あたりにグループ通話ピックアップが有効になっているユーザー総数に対する着信通話の最大速度</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>プールごとに1分あたりにグループ通話ピックアップがあるユーザーによって取得される通話の最大速度</p></td>
<td><p>200</p></td>
<td><p>まで</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>フロントエンドサーバーが8台未満のフロントエンドプールの場合は、測定値を直線的に計算します。 たとえば、フロントエンドプールに1台のフロントエンドサーバーがある場合は、表に示されている値の最大負荷を1/8 として計算します。</P>
> <LI>
> <P>プールあたりのユーザーの最大数を超過しない限り、グループあたりのユーザー数を増減できます。また、グループの数を減らすこともできます。 たとえば、Standard Edition サーバーでは、グループ通話ピックアップが有効になっているユーザーの数がユーザーモデルの最大数 (つまり、25ユーザー3000がグループ通話ピックアップを有効にした場合は 120) の範囲内にあるために、グループごとに25ユーザーの120グループを持つことができます。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

