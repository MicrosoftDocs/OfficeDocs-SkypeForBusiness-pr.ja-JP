---
title: 場所データベースの公開
TOCTitle: 場所データベースの公開
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48273760
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 場所データベースの公開

 

_**トピックの最終更新日:** 2012-10-30_

場所データベースに追加した新しい場所は、公開されるまでクライアントで使用できません。

詳細については、Lync Server 管理シェルのドキュメントで以下のコマンドを参照してください。

  - **Publish-CsLisConfiguration**

緊急位置識別番号 (ELIN) ゲートウェイを使用する場合は、公衆交換電話網 (PSTN) の通信事業者の自動ロケーション識別 (ALI) データベースに ELIN をアップロードする必要があります。ELIN レコードに特定の形式を使用するように PSTN の通信事業者が求める場合があります。詳細については、PSTN の通信事業者に問い合わせてください。場所情報サービス データベースから ELIN レコードをエクスポートし、必要に応じて書式設定することができます。

## 場所データベースを公開するには

  - Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

  - 場所データベースを公開するには、次のコマンドレットを実行します。
    
        Publish-CsLisConfiguration

