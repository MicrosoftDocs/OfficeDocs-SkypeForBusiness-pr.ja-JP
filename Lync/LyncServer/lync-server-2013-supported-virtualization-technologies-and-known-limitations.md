---
title: 'Lync Server 2013: サポートされている仮想化テクノロジと既知の制限'
description: 'Lync Server 2013: サポートされている仮想化テクノロジと既知の制限。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544613"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013 でサポートされている仮想化テクノロジと既知の制限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-02-06_

Lync VDI プラグインは、サポートされている仮想化テクノロジに対して音声およびビデオ通話を許可します。 これにより、microsoft Lync 2010 ホワイトペーパーの「Microsoft Lync Server 2010」に記載されている [クライアント仮想化](https://go.microsoft.com/fwlink/?linkid=330447) の機能が拡張されます。 標準電話の規制に準拠するには、E911 のサポートも含まれています。 次のセクションでは、Lync VDI プラグインによってサポートされる仮想化テクノロジと既知の機能制限について説明します。

<div>

## <a name="support-for-virtualization-technologies"></a>仮想化テクノロジのサポート

Lync VDI プラグインは、個人用仮想デスクトップシナリオでは完全なデスクトップリモート処理をサポートしますが、リモートデスクトップセッションシナリオではサポートしていません。 これらのシナリオは、次のように記述できます。

  - **サポート: カスタマイズされた仮想デスクトップまたは仮想デスクトップインフラストラクチャ (VDI)。**    このシナリオでは、ユーザーごとにカスタマイズ可能な仮想デスクトップにログオンし、セッション間で保持されるファイルをデスクトップに保存することができます。 Microsoft リモートデスクトップサービス、VMware ホライズン表示、および Citrix XenDesktop は、Lync での使用がテストされている実装です。 Microsoft によってテストされたベンダー固有の VDI 環境およびクライアントハードウェアの詳細については、「 [Microsoft Lync 用のインフラストラクチャ認定](https://go.microsoft.com/fwlink/?linkid=313435)」を参照してください。

  - **サポート対象外: リモートデスクトップセッション。**    このシナリオでは、ユーザーごとに、カスタマイズできない汎用の仮想デスクトップセッションにログオンします。 実装の例には、Microsoft リモートデスクトップセッション (RDSH) と citrix XenApp を Citrix レシーバーと組み合わせたものが含まれています。

Lync VDI プラグインは、アプリケーションの仮想化などの他の仮想化テクノロジをサポートしていません。これにより、完全なアプリケーションをローカルにインストールすることなく、アプリケーションを使用できるようになります。 実装の例としては、Citrix XenApp と Microsoft Application Virtualization (App-v) があります。 アプリケーションのストリーミング、アプリケーションのリモート処理、および混合仮想化モード (たとえば、完全なデスクトップリモート処理でのアプリケーションのリモート処理) はサポートされていません。

拡張機能を有効にするために、Lync VDI プラグインは、動的仮想チャネル (DVCs) と呼ばれるプラットフォームに依存しない Api を使用するように設計されています。 Lync で明示的にサポートされていないシナリオについては、「VDI ソリューションプロバイダーからのサポートステートメント」を参照してください。

</div>

<div>

## <a name="known-feature-limitations"></a>既知の機能制限

VDI 環境で Lync 2013 を使用する場合の既知の制限は次のとおりです。

  - 通話委任および応答グループエージェント匿名化機能のサポートには制限があります。

  - 以下の機能はサポートされません。
    
      - 統合オーディオ デバイスとビデオ デバイスのチューニング ページ
    
      - マルチビュービデオ。
    
      - 会話の録音
    
      - リモートデスクトップサービス (RDS)。
    
      - 匿名での会議への参加 (つまり、組織とフェデレーションされない組織によってホストされている Lync 会議への参加)。
    
      - Lync VDI プラグインを Lync Phone Edition デバイスと共に使用します。
    
      - ネットワーク停止時の通話の継続
    
      - カスタマイズされた着信音と音楽の保持機能。

  - Lync VDI プラグインは、Microsoft 365 または Office 365 環境ではサポートされていません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

