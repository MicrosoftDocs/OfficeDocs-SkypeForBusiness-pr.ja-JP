---
title: 'Lync Server 2013: 正規化ルールの定義'
TOCTitle: 正規化ルールの定義
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48273936
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の正規化ルールの定義

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 の正規化ルールでは, .NET Framework 正規表現を使用してダイヤルされた電話番号を E.164 形式に変換します。つまり、正規化ルールにより、ユーザーがダイヤルした電話番号が取得され、当初は Lync Server で使用されていた形式にその番号が変換されます。各ダイヤル プランには、正規化ルールを 1 つ以上割り当てる必要があります。

正規化ルールの詳細については、「計画」のドキュメントの「[Lync Server 2013 のダイヤル プランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。

正規表現の記述方法の詳細については、「.NET Framework の正規表現」( [http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x411)) を参照してください。

以下の方法のどちらかを使用して正規化ルールを定義または編集できます。

  - \[**正規化ルールの構築**\] ツールを使用して、開始桁の数字、長さ、削除する桁数、および追加する数字の値を指定し、その後 Lync Server コントロール パネルに、対応する一致パターンと変換ルールを生成する。

  - 正規表現を手動で記述し、一致パターンと変換ルールを定義する。

## このセクション中

  - [Lync Server 2013 での正規化ルールの構築を使用した正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Lync Server 2013 での手動による正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

## 関連項目

#### タスク

[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)

