---
title: 'Lync Server 2013: 発信通話用のボイス ルートの構成'
TOCTitle: 発信通話用のボイス ルートの構成
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48271835
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での発信通話用のボイス ルートの構成

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 音声ルートは、通話先の電話番号を、1 つ以上の公衆交換電話網 (PSTN) ゲートウェイまたは SIP トランクおよび 1 つ以上の PSTN 使用法レコードに関連付けます。

**Lync Server コントロール パネルを使用して音声ルートを表示するには**

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  \[**音声のルーティング**\] をクリックします。

3.  \[**ルート**\] をクリックします。

4.  音声ルートをダブルクリックし、音声ルートの一覧から追加のプロパティを表示するか、ルートを選択し、\[**編集**\] をクリックします。次に、\[**詳細の表示**\] をクリックします。
    
    > [!NOTE]
    > 一度に 1 つのルートの詳細情報しか表示できません。


**Windows PowerShell を使用して音声ルートを表示するには**

  - Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。Windows PowerShell と **Get-CsVoiceRoute** コマンドレットを使用して、音声ルートを表示できます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。
    
    すべての音声ルートに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsVoiceRoute
    
    次のような情報が表示されます。
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

> [!NOTE]
> 詳細については、「計画」のドキュメントの「<a href="lync-server-2013-voice-routes.md">Lync Server 2013 の音声ルート</a>」を参照してください。


## このセクション中

  - [Lync Server 2013 でのボイス ルートの作成](lync-server-2013-create-a-voice-route.md)

  - [Lync Server 2013 でのボイス ルートの変更](lync-server-2013-modify-a-voice-route.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 での音声ルーティングの管理](lync-server-2013-managing-voice-routing.md)

