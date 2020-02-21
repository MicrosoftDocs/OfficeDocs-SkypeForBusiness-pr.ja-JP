---
title: 'Lync Server 2013: 音声番号の正規化とルーティングの検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f9cd0beea65cfb1718fea3bc1c0235eb7554ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Lync Server 2013 での音声番号の正規化とルーティングの検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-19_

適切な番号の正規化とルーティングは、機能するエンタープライズ Voip 環境にとって非常に重要です。 特に、構内交換 (PBX) からスタンドアロンの Lync Server 環境への移行では、移行を成功させるためのキーの1つは、既存のすべてのダイヤルルールを明らかにして文書化し、適切な正規化ルール、音声ポリシー、およびを作成することです。電話の使用状況とルート。

番号の正規化とルーティングを検証することは、移行時だけでなく、通常のシステムの安定した運用時においても重要です。

Lync server コントロールパネルを使用して毎日この検証を行うことをお勧めします。まず、lync Server のグローバル設定で発行された現在の正規化ルールのセットに対して、堅牢なテストケースのセットを開発することをお勧めします。 これらのテストケースは、ダイヤルプランに対して行われた不要な変更を強調表示するために、毎日実行する必要があります。

Lync Server コントロールパネルを使用すると、音声ルーティングに関する構成情報を視覚化、テスト、変更、アーカイブ、および共有することができます。また、エンタープライズ Voip 番号の正規化ルール、ダイヤルプラン、音声ポリシー、およびルートを変更することもできます。 これには、次のような追加の機能があります。

  - システム間での音声ルーティングデータのエクスポートとインポートまたはバックアップ。

  - ライブシステムにアップロードする前に、構成の変更をテストします。

  - 構成テストケースを作成して実行することにより、データを変更した後、展開されたシステムへの変更をコミットする前に、データをルーティングする際の利便性を高めることができます。

  - 必要な正規表現を記述せずに、数字の正規化ルール、場所のプロファイル、音声ポリシー、およびルーティングデータを作成および変更する。

  - Lync Server Phone Edition との互換性のための場所プロファイルの分析。

  - 音声ルーティングテストの詳細については[、「Lync Server 2013 のテスト用音声ルーティング」](lync-server-2013-test-voice-routing.md)を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

