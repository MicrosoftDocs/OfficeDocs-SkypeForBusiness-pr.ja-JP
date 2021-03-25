---
title: Skype for Business Server の翻訳ルール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Skype for Business Server エンタープライズ VoIP での翻訳ルールとダイヤル文字列の正規化について説明します。
ms.openlocfilehash: d02e4d3b84c03ee40dddbcb9b174adb66dcd6cd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110633"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Skype for Business Server の翻訳ルール

Skype for Business Server エンタープライズ VoIP での翻訳ルールとダイヤル文字列の正規化について説明します。

 エンタープライズ VoIP、逆引き番号参照 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。 変換ルールは、呼び出し番号と通話番号の両方でサポートされます。 Thetrunk ピア (つまり、関連付けられたゲートウェイ、プライベート ブランチ 交換 (PBX)、または SIP トランク) では、番号がローカル ダイヤル形式である必要がある場合があります。 E.164 形式からローカル ダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に、要求 URI を操作する 1 つ以上の変換ルールを定義できます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。

サーバーで送信ルート変換を実行することで、個々のトランク ピアの構成要件を減らして、電話番号をローカル ダイヤル形式に変換できます。 特定の仲介サーバー クラスターに関連付けるゲートウェイとゲートウェイの数を計画する場合は、同様のローカル ダイヤル要件を持つトランク ピアをグループ化すると便利です。 これにより、必要な翻訳ルールの数と書き込みにかかる時間が短縮されます。

> [!IMPORTANT]
> 1 つ以上の変換ルールを エンタープライズ VoIPトランク構成に関連付け、トランク ピアで変換ルールを構成する代わりに使用する必要があります。 2 つのルールが競合する可能性エンタープライズ VoIP、トランク ピアで変換ルールを構成している場合は、変換ルールをトランク構成に関連付けない。

## <a name="example-translation-rules"></a>変換ルールの例

以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。

変換ルールを実装する方法については、「展開」のドキュメントの「[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)」を参照してください。

|**説明**|**先頭の数字**|**Length**|**削除する数字**|**追加する数字**|**一致パターン**|**翻訳**|**例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国内の従来の長距離電話ダイヤル  <br/> ('+' を取り除く)  <br/> |+1  <br/> |ちょうど 12  <br/> |1  <br/> |0  <br/> |^\+(1\d {10} )$  <br/> |$1  <br/> |+14255551010 を 14255551010 に変換  <br/> |
|米国長距離国際電話ダイヤル  <br/> ('+' を削除し、011 を追加)  <br/> |+  <br/> |11 以上  <br/> |1  <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 を 011441235551010 に変換  <br/> |