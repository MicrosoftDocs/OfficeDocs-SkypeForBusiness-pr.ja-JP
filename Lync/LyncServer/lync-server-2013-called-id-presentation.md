---
title: 受信者番号の提示
TOCTitle: 受信者番号の提示
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49887154
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 受信者番号の提示

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2010 では、呼び出し先の電話番号 (呼び出された電話番号) を E.164 形式から、*トランク ピア* (関連付けられているゲートウェイ、構内交換機 (PBX)、または SIP トランク) で必要なローカルのダイヤル形式に変換できます。これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。


> [!IMPORTANT]
> 1 つ以上の変換ルールをエンタープライズ VoIP のトランク構成と関連付ける機能は、トランク ピアで変換ルールを構成することの<EM>代替手段</EM>として使用されることを目的としています。トランク ピアで変換ルールを構成した場合は、2 つのルールが競合する可能性があるため、変換ルールをエンタープライズ VoIP トランク構成に関連付けないでください。



次のいずれかの方法を使用して、変換ルールを作成または変更できます。

  - \[**変換ルールの構築**\] ツールを使用して、先頭の数字、長さ、削除する数字と追加する数字の値を指定してから、Lync Server コントロール パネル で対応する一致パターンと変換ルールを生成する。

  - 正規表現を手動で記述し、一致パターンと変換ルールを定義する。

> [!NOTE]
> 正規表現の記述方法については、「.NET Framework の正規表現」(<a href="http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=140927&amp;clcid=0x411</a>) を参照してください。


## このセクション中

  - [変換ルールの構築ツールを使用した変換ルールの作成または変更](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [手動による変換ルールの作成または変更](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

## 関連項目

#### 概念

[Lync Server 2013 発信者番号の提示](lync-server-2013-caller-id-presentation.md)

