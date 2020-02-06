---
title: Skype for Business Server の翻訳ルール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice での翻訳ルールとダイヤル文字列の正規化について説明します。
ms.openlocfilehash: c82b925c9ef168d8a5f5e7ac730a93a53a432e2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802397"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Skype for Business Server の翻訳ルール

Skype for Business Server Enterprise Voice での翻訳ルールとダイヤル文字列の正規化について説明します。

 エンタープライズボイスでは、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列が E.i 形式に正規化されている必要があります。 翻訳ルールは、電話番号と通話番号の両方でサポートされています。 トランクピア (つまり、関連付けられているゲートウェイ、プライベートブランチ exchange (PBX)、または SIP トランク) では、電話番号が市内ダイヤル形式になっている必要があります。 E.164 形式から地域のダイヤル形式に番号を変換するには、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。

サーバーで送信ルートの翻訳を実行すると、電話番号をローカルのダイヤル形式に変換するために、個々のトランクピアの構成要件を減らすことができます。 ゲートウェイとゲートウェイの数を計画しているときに、特定の仲介サーバークラスターと関連付けるには、同様のローカルダイヤル要件でトランクピアをグループ化すると便利な場合があります。 これにより、必要な翻訳ルールの数と書き込みにかかる時間を減らすことができます。

> [!IMPORTANT]
> 1つまたは複数の翻訳ルールをエンタープライズボイストランク構成に関連付けることは、トランクピアでの翻訳ルールの設定の代わりとして使用する必要があります。 トランクピアで翻訳ルールを構成している場合は、2つのルールが競合する可能性があるため、翻訳ルールをエンタープライズボイストランク構成に関連付けないでください。

## <a name="example-translation-rules"></a>変換ルールの例

以下の変換ルールの例では、トランク ピアについて E.164 形式からローカル形式に番号を変換するルールをサーバー上に作成する方法を示しています。

変換ルールを実装する方法については、「展開」のドキュメントの「[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)」を参照してください。

|**説明**|**先頭の数字**|**長さ**|**削除する数字**|**追加する数字**|**照合パターン**|**変換**|**例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|米国内の従来の長距離電話ダイヤル  <br/> (「+」を取り除きます)  <br/> |+1  <br/> |ちょうど 12  <br/> |1  <br/> |0  <br/> |^\+(1 \ d{10}) $  <br/> |$1  <br/> |+14255551010 を 14255551010 に変換  <br/> |
|米国長距離国際電話ダイヤル  <br/> (「+」をタップして、011を追加)  <br/> |+  <br/> |11 以上  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011$1  <br/> |+441235551010 を 011441235551010 に変換  <br/> |


