---
title: 'Lync Server 2013: 会議での位置情報に基づくルーティングの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の位置情報に基づくルーティングの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-19_

場所に基づくルーティング会議アプリケーションをインストールして構成するために必要な要件を次に示します。

  - Lync Server 2013 累積更新プログラム2は、トポロジ内のすべてのサーバーまたはプールに展開する必要があります。

<div>


> [!NOTE]  
> トポロジ内の Lync サーバーまたはプールに Lync Server 2013 累積更新プログラム2以降がインストールされていない場合、Lync 会議の位置情報に基づくルーティングの適用は保証されません。



</div>

  - Lync Server 2013 の場所に基づくルーティングは、位置ベースのルーティング会議アプリケーションの前提条件です。 Lync Server 2013 の場所に基づくルーティングの構成の詳細については、「[場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)」を参照してください。

  - 位置に基づくルーティング会議アプリケーションの要件は、Lync Server 2013 の場所に基づくルーティングの要件と同じです。 詳細については、「[場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)」を参照してください。

<div>

## <a name="supported-servers"></a>サポートされているサーバー

場所に基づくルーティング会議アプリケーションを使用するには、Lync Server 2013 累積更新プログラム2が、トポロジ内のすべてのフロントエンドプールおよび標準エディションのサーバーに展開されている必要があります。 Lync Server 2013 累積更新プログラム2が、トポロジ内の一部の Lync サーバーにインストールされていない場合、場所に基づくルーティングの制限は、Lync 会議とコンサルティングによる通話転送に完全に適用することはできません。

次の表は、場所に基づくルーティングをサポートするサーバーの役割とバージョンの組み合わせを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>フロント エンド プールのバージョン</p></td>
<td><p>仲介サーバーのバージョン</p></td>
<td><p>サポート対象</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム 2</p></td>
<td><p>Lync Server 2013 累積更新プログラム 2</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累積更新プログラム 2</p></td>
<td><p>Lync Server 2013 累積更新プログラム 1</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累積更新プログラム 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム 1</p></td>
<td><p>任意</p></td>
<td><p>不可</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>不可</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>不可</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>サポートされているクライアント

Lync 会議の位置情報に基づくルーティングをサポートする Lync クライアントは、Lync Server 2013 の場所に基づくルーティングをサポートしているクライアントと同じです。 詳細については、「[場所に基づくルーティングのクライアントとサーバーのサポート](lync-server-2013-client-and-server-support-for-location-based-routing.md)」を参照してください。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>提案型通話転送の仲介サーバー要件

位置情報に基づくルーティング会議アプリケーションでは、提案型の通話転送についての位置情報に基づくルーティング制限を適用するために、スタンドアロンの仲介サーバーを展開する必要があります。

提案型の通話転送の位置情報に基づくルーティングを適用するには、位置情報に基づくルーティングが必要なネットワーク領域で、仲介サーバーが1つの仲介サーバーピア (PBX、SIP ゲートウェイなど) と関連付けられている必要があります。 追加の仲介サーバーピアが同じネットワーク領域に展開されている場合、仲介サーバーピアは、別の仲介サーバーと関連付けられている必要があります。 この要件は、次のように詳細に説明します。

  - 複数の仲介サーバーピアに対して1つの仲介サーバーを使用して、複数の SIP trunks で構成されている仲介サーバーを経由して仲介サーバーピアにルーティングされる場合 (Pbx とゲートウェイ)、コンサルティング一部の SIP trunks で提案型通話転送が許可されていても、他の SIP trunks では許可されていない場合は、着信転送がブロックされています。
    
    たとえば、PSTN ゲートウェイ仲介サーバーピアと PBX 仲介サーバーピアをサービスしている単一の仲介サーバーの場合、次の動作が監視されます。
    
      - 特定のサイトの Lync ユーザー (つまり、サイト 1) から別のサイト (つまり、サイト 2) の Lync ユーザーに対して、提案型転送を使用して通話を転送しようとすると、PSTN の有料通話を防ぐことはできません。
    
      - 特定のサイトの Lync ユーザー (サイト 1) と、別のサイト (サイト 1) の PBX エンドポイントを使用して、別のサイト (サイト 2) との通話を発信しようとしたときに、tol の可能性がある場合でも、通話は許可されません。l バイパス。

  - 仲介サーバーピアごとに個別の仲介サーバー
    
    提案型転送が仲介サーバーピアを対象としている場合は、仲介サーバーによって処理される単一の仲介サーバーピアに対して、コンサルティング転送が評価されます。 この通話は、サイト内の他のすべての Mediations サーバーピアが、個別の仲介サーバーによってサービスされている場合でも、PSTN の有料電話による通話は許可されません。
    
    たとえば、PSTN ゲートウェイ仲介サーバーピアと PBX 仲介サーバーピアをサービスしている別個の仲介サーバーがある場合は、次の動作が監視されます。
    
      - 特定のサイトの Lync ユーザー (つまり、サイト 1) から別のサイト (つまり、サイト 2) の Lync ユーザーに対して、提案型転送を使用して通話を転送しようとすると、PSTN の有料通話を防ぐことはできません。
    
      - 指定したサイトの Lync ユーザー (サイト 1) と、別のサイト (サイト 1) の PBX エンドポイントを使用して、別のサイト (サイト 2) との通話を提案転送によって転送しようとすると、PSTN 通話の可能性があるため、通話が許可されません。あげる.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>場所に基づくルーティング会議アプリケーションでサポートされていない機能

場所に基づくルーティング会議アプリケーションでは、次の機能はサポートされていません。

  - ダイヤルイン会議。 位置情報に基づくルーティングは、ダイヤルイン会議には適用できません。 会議開催者が位置情報に基づくルーティングを有効にしている Lync ユーザーであっても、特定の会議へのダイヤルイン要求は、位置情報に基づくルーティングで制限されません。

  - 場所に基づくルーティング制限を適用する必要がある地域では、会議アクセス番号をプロビジョニングしないことをお勧めします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

