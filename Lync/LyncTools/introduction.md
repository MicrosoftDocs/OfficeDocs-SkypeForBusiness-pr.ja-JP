---
title: 概要
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

Lync Server 2013 のストレスとパフォーマンスツール (LyncPerfTool とも呼ばれます) では、次の種類のユーザーロードをシミュレートできます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>インスタントメッセージング (IM) とプレゼンス</p></td>
<td><p>電話会議</p></td>
</tr>
<tr class="even">
<td><p>アプリケーション共有</p></td>
<td><p>VoIP (公衆交換電話網 (PSTN) シミュレーションを含む) ボイスオーバー IP (VoIP)</p></td>
</tr>
<tr class="odd">
<td><p>Web Access クライアント会議</p></td>
<td><p>Microsoft Lync 2013 アテンダント</p></td>
</tr>
<tr class="even">
<td><p>応答グループ</p></td>
<td><p>配布リストの展開</p></td>
</tr>
<tr class="odd">
<td><p>アドレス帳のダウンロードとアドレス帳のクエリ</p></td>
<td><p>拡張 9-1-1 (E9) 通話と位置情報プロファイル (ダイヤルプラン)</p></td>
</tr>
<tr class="even">
<td><p>MultiView</p></td>
<td><p>会議から複数のストリームを表示する</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Lync Server 2013 のストレスとパフォーマンスツールは、高度な構成のみを通じて、クロスプールの負荷生成とフェデレーションをサポートします。

このツールでは、次のクライアントのユーザーロードもシミュレートされません。

  - Office Live Meeting 2007

  - Lync 2013 常設チャット

このため、Lync Server 2013 のストレスとパフォーマンスツールは、次のコンポーネントのテストをサポートしていません。

  - Lync 2013 常設チャット

  - Exchange の統合シナリオ

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 のストレスとパフォーマンスツールに含まれているアプリケーションとファイル

Lync Server 2013 のストレスとパフォーマンスツールには、次のアプリケーションが含まれています。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ツール</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Userプロビジョニングツール .exe</p></td>
<td><p>Lync Server 2013 ユーザープロビジョニングツール。 このツールは、ユーザーと連絡先を作成するために使用されます。</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator</p></td>
<td><p>Lync Server 2013 のロード構成ツール。 このツールは、シミュレートするためのユーザーロードの特性を構成するために使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool</p></td>
<td><p>Lync Server 2013 ストレスおよびパフォーマンスツール。 LyncPerfTool は、ユーザーロードをシミュレートするツールです。</p></td>
</tr>
<tr class="even">
<td><p>Tmx</p></td>
<td><p>Lync Server 2013 ログツールを使用するには、tmx が必要です。</p></td>
</tr>
<tr class="odd">
<td><p>プロビジョニングスクリプトの例</p></td>
<td><p>次の例は、特定のシナリオに基づいて、ロードテストを実行するためのトポロジを構成するために使用されます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

