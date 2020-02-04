---
title: 'Lync Server 2013: 音声番号の正規化とルーティングを検証する'
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
ms.openlocfilehash: 16739595878b0c67b37f988295a4b02877a3a6fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>Lync Server 2013 での音声番号の正規化とルーティングの検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-19_

正しい番号の正規化とルーティングは、機能的なエンタープライズ Voip 環境で非常に重要です。 特に、プライベートブランチ exchange (PBX) から単体の Lync Server 環境に移行する場合、移行を成功させるためのキーの1つとして、既存のすべてのダイヤルルールを表示して文書化し、適切な正規化ルール、音声ポリシー、電話の使用状況とルート。

番号の正規化とルーティングは、移行時だけでなく、通常どおりにシステムの安定した操作を実行する場合にも重要です。

この検証は、lync server コントロールパネルを使用して、Lync Server のグローバル設定で公開された現在の正規化ルールのセットとの堅固なテストケースの開発を開始することをお勧めします。 これらのテストケースは、ダイヤルプランに加えられた不要な変更を強調表示するために、毎日実行する必要があります。

Lync Server コントロールパネルは、音声ルーティングに関する構成情報の視覚化、テスト、変更、アーカイブ、共有にも役立ちます。また、エンタープライズのボイス番号正規化規則、ダイヤルプラン、音声ポリシー、ルートを変更することもできます。 次の操作を実行するための追加機能が用意されています。

  - システム間でのボイスルーティングデータのエクスポートとインポートまたはバックアップ。

  - ライブシステムにアップロードする前に構成の変更をテストする。

  - 構成テストケースを作成し、実行して、そのデータを変更した後、展開されたシステムへの変更をコミットする前に、ルーティングの操作性を向上させることができます。

  - 数値正規化ルール、位置情報プロファイル、音声ポリシー、および必要な正規表現を記述せずにデータをルーティングする。

  - Lync Server Phone Edition との互換性を保つために、位置情報プロファイルを分析します。

  - 音声ルーティングテストの詳細については[、「Lync Server 2013 でのボイスルーティングのテスト」](lync-server-2013-test-voice-routing.md)を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

