---
title: 'Lync Server 2013: 会議用の Location-Based ルーティングの要件'
description: 'Lync Server 2013: 会議用の Location-Based ルーティングの要件。'
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
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542523"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の Location-Based ルーティングの要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-19_

Location-Based ルーティング会議アプリケーションをインストールして構成するために必要な要件は次のとおりです。

  - Lync Server 2013 の累積的な更新プログラム2を、トポロジ内のすべてのサーバーまたはプールに展開する必要があります。

<div>


> [!NOTE]  
> トポロジ内の Lync server またはプールに Lync Server 2013 の累積的な更新プログラム2以降がインストールされていない場合、Lync 会議の Location-Based ルーティングを行うことは保証できません。



</div>

  - Lync Server 2013 Location-Based ルーティングは Location-Based ルーティング会議アプリケーションの前提条件です。 Lync Server 2013 Location-Based ルーティングの構成の詳細については、「 [Location-Based ルーティングを構成](lync-server-2013-configuring-location-based-routing.md)する」を参照してください。

  - Location-Based ルーティング会議アプリケーションの要件は、Lync Server 2013 Location-Based ルーティングの要件と同じです。 詳細については、「 [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md)」を参照してください。

<div>

## <a name="supported-servers"></a>サポートされるサーバー

Location-Based ルーティング会議アプリケーションでは、Lync Server 2013 の累積更新プログラム2が、トポロジ内のすべての Front-End プールおよび Standard Edition サーバーに展開されている必要があります。 トポロジ内の一部の Lync サーバーに Lync Server 2013 の累積的な更新プログラム2がインストールされていない場合は、Lync 会議と提案型の通話の転送に Location-Based ルーティングの制限を完全に適用することはできません。

次の表は、Location-Based ルーティングをサポートするサーバーの役割とバージョンの組み合わせを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Front-End プールのバージョン</p></td>
<td><p>仲介サーバーのバージョン</p></td>
<td><p>サポート</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>Lync Server 2013 累積更新プログラム2</p></td>
<td><p>必要</p></td>
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

Lync 会議の Location-Based ルーティングをサポートする Lync クライアントは、Lync Server 2013 Location-Based ルーティングをサポートするクライアントと同じです。 詳細については、 [Location-Based ルーティングのクライアントとサーバーのサポート](lync-server-2013-client-and-server-support-for-location-based-routing.md)を参照してください。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>コンサルティング呼び出しの転送に関する仲介サーバーの要件

Location-Based ルーティング会議アプリケーションは、スタンドアロンの仲介サーバーを展開する必要があります。これには、提案型呼び出しの転送に関する Location-Based ルーティングの制限を適用する必要があります。

コンサルティング呼び出し転送の Location-Based ルーティングを強制するには、仲介サーバーが、Location-Based ルーティングが必要なネットワーク地域で、1つの仲介サーバーピア (PBX、SIP ゲートウェイなど) にのみ関連付けられている必要があります。 別の仲介サーバーピアが同じネットワーク地域に展開されている場合は、仲介サーバーのピアを別の仲介サーバーに関連付ける必要があります。 この要件は、次のように詳細に説明されています。

  - 複数の仲介サーバーピアごとに1つの仲介サーバー。複数の SIP トランクで構成されている仲介サーバー (Pbx およびゲートウェイ) に対して、コンサルティング呼び出し転送が仲介サーバーのピアにルーティングされる場合、一部の SIP トランクでコンサルティング呼び出しの転送が許可されているが、他の SIP トランクでは許可されていない場合は、
    
    たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアを1つの仲介サーバーでサービスしている場合は、次の動作が確認されます。
    
      - 特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。
    
      - 特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) 内の PBX エンドポイントとの通話を、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに転送しようとすると、PSTN の有料の通話が行われない場合でも通話が許可されません。

  - 仲介サーバーピアごとに別々の仲介サーバー
    
    コンサルティング転送が仲介サーバーピアを対象にしている場合は、仲介サーバーによって提供される単一の仲介サーバーピアに対して、コンサルティング転送が評価されます。 この通話は、サイト内の他のすべての Mediations いるサーバーピアが個別の仲介サーバーによって処理されている場合でも、PSTN の有料通話で発生する可能性に基づいて許可または拒否されます。
    
    たとえば、PSTN ゲートウェイ仲介サーバーのピアと PBX 仲介サーバーのピアをサービスしている個別の仲介サーバーの場合、次の動作が確認されます。
    
      - 特定のサイト (サイト 1) からの Lync ユーザーが、提案転送を介して別のサイト (つまり、サイト 2) から Lync ユーザーに通話を転送しようとすると、その通話は PSTN の有料サービスを回避することを許可されません。
    
      - 特定のサイトの Lync ユーザー (サイト 1) が、別のサイト (サイト 1) の PBX ユーザーに対して、提案転送を介して別のサイト (つまり、サイト 2) からの通話を転送しようとすると、その通話は PSTN の有料の通話がバイパスされる可能性があるため許可されます。

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Location-Based ルーティング会議アプリケーションでサポートされていない機能

Location-Based ルーティング会議アプリケーションでは、次の機能はサポートされていません。

  - ダイヤルイン会議。 ダイヤルイン会議に Location-Based ルーティングを強制することはできません。 会議開催者が Location-Based ルーティングを有効にしている Lync ユーザーであっても、特定の会議に対するダイヤルイン要求は Location-Based ルーティングによって制限されません。

  - Location-Based ルーティング制限を適用する必要がある地域では、会議アクセス番号をプロビジョニングしないことをお勧めします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

