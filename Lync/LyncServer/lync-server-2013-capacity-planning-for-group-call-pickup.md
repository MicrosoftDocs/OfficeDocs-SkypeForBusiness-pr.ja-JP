---
title: 'Lync Server 2013: グループ通話のピックアップのキャパシティ計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 でのグループ通話の集配のキャパシティ計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-12_

<div id="sectionSection0" class="section">

次の表では、キャパシティ計画の要件の基礎として使用できるグループ通話ピックアップユーザーモデルについて説明します。

<div>


> [!IMPORTANT]  
> グループ通話のピックアップは、コールパークアプリケーションに基づいています。 障害復旧のキャパシティ計画の場合、ペアプールの各プールでは、両方のプールのグループ通話のピックアップを含む、コールパークサービスのワークロードを処理できる必要があることに注意してください。



</div>

### <a name="group-call-pickup-user-model"></a>グループ通話のピックアップユーザーモデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指標</th>
<th>フロントエンドプールあたり (8 個のフロントエンドサーバーを含む)</th>
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
<td><p>推奨グループ数</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>プールあたりの、グループ通話ピックアップが可能な最大ユーザー数</p></td>
<td><p>25,000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>プールおよび分あたりの、グループ通話ピックアップが可能な総ユーザー数に対する着信通話数の最大比率</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>プールおよび分あたりの、グループ通話ピックアップによって取得される通話数の最大比率</p></td>
<td><p>200</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>フロントエンドサーバーの数が8個以下のフロントエンドプールの場合は、数値を直線的に計算します。 たとえば、フロントエンドプールに1つのフロントエンドサーバーがある場合は、テーブルに表示されている値の1/8 としての最大読み込みを計算します。</P>
> <LI>
> <P>プールあたりのユーザー数の上限を超えていない限り、1つのグループに対して推奨されるユーザー数とグループ数を増減できます。 たとえば、グループ通話のピックアップ用に有効になっているユーザーの数がユーザーモデルの最大数 (120 グループの場合は、グループ通話のピックアップでは3000ユーザー) のままであるため、標準エディションのサーバーではグループあたり25人のユーザーを持つ120グループを持つことができます。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

