---
title: 'Lync Server 2013: 環境テストに関する問題'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 812796be0589342f346cfc6755ace64cb402f63a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514084"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013 での環境テストに関する問題

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

ベストプラクティスアナライザーには、Lync Server 2013 環境がサポートされている構成であることを確認する方法が用意されています。 Active Directory ドメインサービスのチェックの一部として、ベストプラクティスアナライザーは次の処理を行います。

  - Active Directory ドメインサービスのフォレストとスキーマの準備を検証します。

  - 展開内の Active Directory ドメインサービスのサイトとドメインの数を示します。

  - フォレストとドメインのレベルを確認します。

  - ドメインコントローラーのバージョンを確認します。

  - ドメイン、構成、およびスキーマの名前付けコンテキストを識別します。

  - 有効なユーザーの数を識別します。

  - グローバル Active Directory ドメインサービス設定が保存されている場所をチェックします。

  - Lync Server のサービス接続ポイント (Scp) を確認します。

  - データベースバージョンを識別します。

<div>

## <a name="resolving-issues-with-the-environment"></a>環境に関する問題の解決

環境テストで問題が検出された場合、これらの問題は、Active Directory の構成の問題、または特定のサーバーで実行されているソフトウェアのレベルによって発生する可能性があります。 たとえば、ベストプラクティスアナライザーが Windows Server 2000 を実行している環境内のドメインコントローラーを識別する場合は、警告を発行し、それらのドメインコントローラーをサポートされているバージョンの Windows Server にアップグレードする必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

