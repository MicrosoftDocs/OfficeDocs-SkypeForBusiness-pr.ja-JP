---
title: 'Lync Server 2013: サポートされる仮想化テクノロジと既知の制限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013 でサポートされる仮想化テクノロジと既知の制限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-02-06_

Lync VDI プラグインを使うと、サポートされている仮想化テクノロジで音声とビデオ通話を行うことができます。 これにより、microsoft Lync 2010 ホワイトペーパーの[クライアント仮想化](https://go.microsoft.com/fwlink/?linkid=330447)での Microsoft lync Server 2010 について説明されている機能が拡張されます。 標準的な電話の規制に準拠するため、E911 のサポートも含まれています。 以下のセクションでは、Lync VDI プラグインでサポートされている仮想化テクノロジと既知の機能の制限について説明します。

<div>

## <a name="support-for-virtualization-technologies"></a>サポートされている仮想化テクノロジ

Lync VDI プラグインは、個人用仮想デスクトップシナリオでは完全なデスクトップリモート処理をサポートしていますが、リモートデスクトップセッションのシナリオではサポートしていません。 これらのシナリオは、次のように記述できます。

  - **サポート: カスタマイズされた仮想デスクトップまたは仮想デスクトップインフラストラクチャ (VDI)。**   このシナリオでは、各ユーザーがカスタマイズ可能な仮想デスクトップにログオンし、セッション間で保持されるファイルをデスクトップに保存することができます。 Microsoft リモートデスクトップサービス、VMware ホライズンビュー、Citrix XenDesktop は、Lync での使用がテストされている実装です。 Microsoft によってテストされたベンダー固有の VDI 環境とクライアントハードウェアの詳細については、「 [Microsoft Lync のインフラストラクチャ認定](https://go.microsoft.com/fwlink/?linkid=313435)」を参照してください。

  - **サポートされていません: リモートデスクトップセッション。**   このシナリオでは、各ユーザーが、カスタマイズできない汎用の仮想デスクトップセッションにログオンします。 このような実装の例には、マイクロソフト リモート デスクトップ セッション (RDSH) や Citrix XenApp と Citrix Receiver の組み合わせがあります。

Lync VDI プラグインは、アプリケーションの仮想化などの他の仮想化テクノロジをサポートしていません。これにより、完全なアプリケーションをローカルでインストールする必要なく、アプリケーションを使用できるようになります。 実装の例には、Citrix XenApp と Microsoft Application Virtualization (App-v) が含まれます。 アプリケーションのストリーミング、アプリケーションのリモート処理、および混合型の仮想化モード (たとえば、完全なデスクトップリモート処理におけるアプリケーションのリモート処理) はサポートされていません。

拡張性を許可するために、Lync VDI プラグインは動的仮想チャネル (DVCs) と呼ばれるプラットフォームに依存しない Api を使うように設計されています。 Lync で明示的にサポートされていないシナリオについては、「VDI ソリューションプロバイダーのサポートステートメント」を参照してください。

</div>

<div>

## <a name="known-feature-limitations"></a>既知の機能制限

VDI 環境で Lync 2013 を使用する場合は、次のような制限があります。

  - 通話の委任と応答グループのエージェント匿名化) 機能は、制限されています。

  - 以下の機能はサポートされません。
    
      - 統合オーディオ デバイスとビデオ デバイスのチューニング ページ
    
      - マルチビュー ビデオ
    
      - 会話の録音
    
      - リモートデスクトップサービス (RDS)。
    
      - 会議への匿名参加 (つまり、組織とフェデレーションされていない組織によってホストされている Lync 会議への参加)。
    
      - Lync VDI プラグインと Lync Phone Edition デバイスの併用。
    
      - ネットワーク停止時の通話の継続
    
      - 保留機能の着信音と音楽のカスタマイズ

  - Lync VDI プラグインは、Office 365 環境ではサポートされていません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

