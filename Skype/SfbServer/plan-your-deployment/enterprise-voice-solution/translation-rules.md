---
title: Skype for Business Server の変換ルール
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
description: Skype for Business Server エンタープライズ VoIP での変換ルールとダイヤル文字列正規化について説明します。
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802687"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Skype for Business Server の変換ルール

Skype for Business Server エンタープライズ VoIP での変換ルールとダイヤル文字列正規化について説明します。

 エンタープライズ VoIP、逆引き番号検索 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。 変換ルールは、呼び出し元の番号と呼び出し元の番号の両方でサポートされます。 トランク ピア (つまり、関連付けられたゲートウェイ、PBX (PBX)、または SIP トランク) では、番号がローカル ダイヤル形式である必要がある場合があります。 E.164 形式からローカルダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に、1 つ以上の変換ルールを定義して要求 URI を操作できます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。

サーバーで発信ルート変換を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランク ピアの構成要件を減らできます。 特定の仲介サーバー クラスターに関連付けるゲートウェイとゲートウェイの数を計画する場合、同様のローカル ダイヤル要件を持つトランク ピアをグループ化すると便利な場合があります。 これにより、必要な変換ルールの数と書き込みにかかる時間が短縮されます。

> [!IMPORTANT]
> 1 つ以上の変換ルールを エンタープライズ VoIP トランク構成に関連付け、トランク ピアで変換ルールを構成する代わりに使用する必要があります。 2 つのルールが競合する可能性エンタープライズ VoIPトランク ピアで変換ルールを構成している場合は、変換ルールをトランク構成に関連付けない。

## <a name="example-translation-rules"></a>変換ルールの例

以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。

変換ルールを実装する方法については、「展開」のドキュメントの「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。

|**説明**|**先頭の数字**|**Length**|**削除する数字**|**追加する数字**|**一致パターン**|**翻訳**|**例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国内の従来の長距離電話ダイヤル  <br/> ('+' を取り除く)  <br/> |+1  <br/> |ちょうど 12  <br/> |1   <br/> |0  <br/> |^\+(1\d {10} )$  <br/> |$1  <br/> |+14255551010 を 14255551010 に変換  <br/> |
|米国長距離国際電話ダイヤル  <br/> ('+' を削除して 011 を追加)  <br/> |+  <br/> |11 以上  <br/> |1   <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 を 011441235551010 に変換  <br/> |


