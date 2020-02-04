---
title: 'フェーズ 10: レガシサイトの廃止'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>フェーズ 10: レガシサイトの廃止

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

次のトピックでは、Office Communications Server 2007 R2 のレガシ展開でのプールの廃止、サーバーとプールの無効化と削除に関するガイダンスを提供します。 このセクションに記載されているすべての手順を行う必要はありません。 以下の各トピックの情報を読み、使用する使用停止手順を確認してください。

<div>


> [!WARNING]  
> ダイヤルイン会議用の会議ディレクトリを Lync Server 2013 にインポートした場合は、プールの廃止を開始する前に、会議ディレクトリの所有権を Lync Server 2013 に移行することが重要です。 最初に会議ディレクトリの所有権を移行することなくプールを廃止すると、移行したすべての会議のダイヤルイン機能が機能しなくなります。 従来のプールの各会議ディレクトリについて、所有権を1回移行する手順を実行する必要があります。



</div>

<div>


> [!IMPORTANT]  
> Microsoft ユニファイドコミュニケーションマネージ API (UCMA) アプリケーションの移行とアップグレードに関する情報については、「従来の環境を廃止する前に」を参照してください。<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [会議ディレクトリを移動する](move-conference-directories.md)

  - [DNS SRV レコードの更新](update-dns-srv-records_1.md)

  - [サーバーとプールの無効化](decommissioning-servers-and-pools.md)

  - [BackCompatSite を削除する](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

