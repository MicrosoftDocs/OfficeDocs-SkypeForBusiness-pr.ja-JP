---
title: 'Lync Server 2013: 会議の場所に基づくルーティングの要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 567cebd5fcf1fc2a60fa110754f916525052e57d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の場所に基づくルーティングの要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-19_

場所に基づくルーティング会議アプリケーションをインストールして構成するために必要な要件は次のとおりです。

  - Lync Server 2013 の累積的な更新プログラム2を、トポロジ内のすべてのサーバーまたはプールに展開する必要があります。

<div>


> [!NOTE]  
> トポロジ内の Lync server またはプールに Lync Server 2013 の累積的な更新プログラム2以降がインストールされていない場合、Lync 会議の場所に基づくルーティングの適用は保証できません。



</div>

  - Lync Server 2013 の場所に基づくルーティングは、場所に基づくルーティング会議アプリケーションの前提条件です。 Lync Server 2013 の場所に基づくルーティングの構成の詳細については、「[場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)」を参照してください。

  - 場所に基づくルーティング会議アプリケーションの要件は、Lync Server 2013 の場所に基づくルーティングの要件と同じです。 詳細については、「[場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)」を参照してください。

<div>

## <a name="supported-servers"></a>サポートされるサーバー

場所に基づくルーティング会議アプリケーションを使用するには、Lync Server 2013 の累積的な更新プログラム2が、トポロジ内のすべてのフロントエンドプールおよび Standard Edition サーバーに展開されている必要があります。 Lync Server 2013 の累積的な更新プログラム2が、トポロジ内の一部の Lync サーバーにインストールされていない場合は、Lync 会議とコンサルティング呼び出しの転送に対して、場所に基づくルーティング制限を完全に適用することはできません。

次の表は、場所に基づくルーティングをサポートするサーバーの役割とバージョンの組み合わせを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>フロントエンドプールのバージョン</p></td>
<td><p>仲介サーバーのバージョン</p></td>
<td><p>サポート済み</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>はい</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>Lync Server 2013 累積更新プログラム1</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム1</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>いいえ</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>サポートされるクライアント

Lync 会議の場所に基づくルーティングをサポートする Lync クライアントは、Lync Server 2013 の場所に基づくルーティングをサポートするクライアントと同じです。 詳細については、「[クライアントとサーバーのサポート](lync-server-2013-client-and-server-support-for-location-based-routing.md)」を参照してください。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>コンサルティング呼び出しの転送に関する仲介サーバーの要件

場所に基づくルーティング会議アプリケーションは、スタンドアロンの仲介サーバーを展開する必要があります。これには、提案型の通話の転送に対して、場所に基づくルーティングの制限を適用する必要があります。

提案型呼び出しの転送の場所ベースのルーティングを適用するには、場所に基づくルーティングが必要なネットワーク地域で、仲介サーバーが1つの仲介サーバーピア (PBX、SIP ゲートウェイなど) にのみ関連付けられている必要があります。 別の仲介サーバーピアが同じネットワーク地域に展開されている場合は、仲介サーバーのピアを別の仲介サーバーに関連付ける必要があります。 この要件は、次のように詳細に説明されています。

  - 複数の仲介サーバーピアごとに1台の仲介サーバー複数の SIP トランクを使用して構成されている仲介サーバーを使用して、コンサルティングによる転送が仲介サーバーのピアにルーティングされる場合 (Pbx およびゲートウェイ)、提案一部の SIP トランクでコンサルティング呼び出し転送が許可されていても、他の SIP トランク経由では許可されていない場合、通話転送は PSTN の有料電話を回避するためにブロックされます。
    
    たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアを1つの仲介サーバーでサービスしている場合は、次の動作が確認されます。
    
      - 特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。
    
      - 特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) 内の PBX エンドポイントとの通話を、提案転送を介して別のサイトの Lync ユーザーに転送しようとすると、その通話は PSTN tol の可能性がある場合でも許可されません。l バイパス。

  - 仲介サーバーピアごとに別々の仲介サーバー
    
    コンサルティング転送が仲介サーバーピアを対象にしている場合は、仲介サーバーによって提供される単一の仲介サーバーピアに対して、コンサルティング転送が評価されます。 この通話は、サイト内の他のすべての Mediations いるサーバーピアが個別の仲介サーバーによって処理されている場合でも、PSTN の有料通話で発生する可能性に基づいて許可または拒否されます。
    
    たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアをサービスしている個別の仲介サーバーの場合、次の動作が確認されます。
    
      - 特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。
    
      - 特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) の PBX ユーザーに対して、提案転送を介して別のサイトの (サイト 2) の通話を転送しようとすると、その通話は許可されますが、PSTN の有料電話のバイパスでは発生しません。留守番.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>場所に基づくルーティング会議アプリケーションでサポートされていない機能

次の機能は、場所に基づくルーティング会議アプリケーションではサポートされていません。

  - ダイヤルイン会議。 ダイヤルイン会議に対して、場所に基づくルーティングを強制することはできません。 会議開催者が場所に基づくルーティングを有効にした Lync ユーザーであっても、特定の会議に対するダイヤルイン要求は、場所に基づいたルーティングによって制限されることはありません。

  - 場所に基づくルーティング制限を適用する必要がある地域では、会議アクセス番号をプロビジョニングしないことをお勧めします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

