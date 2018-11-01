---
title: 仲介サーバーを構成する
TOCTitle: 仲介サーバーを構成する
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48272182
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 仲介サーバーを構成する

 

_**トピックの最終更新日:** 2016-12-08_

ここでは、従来の Office Communications Server 2007 R2 仲介サーバーではなく Lync Server 2013 仲介サーバーを使用するように Lync Server 2013 プールを構成する手順の詳細について説明します。

サーバーの役割を追加または削除する際に、トポロジを正常に公開したり、有効または無効にするには、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。サーバーの役割を追加するための適切な管理者権限およびアクセス許可を委任することもできます。詳細については、Standard Edition サーバーまたは Enterprise Edition サーバーの「展開」のドキュメントの「セットアップのアクセス許可の委任」を参照してください。他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

> [!NOTE]
> Lync Server 2013 との連携が認定されている PSTN ゲートウェイ、IP-PBX、および SIP トランキング サービスの最新情報については、「Microsoft Unified Communications Open Interoperability Program - Office Communications Server (英語)」( <a href="http://go.microsoft.com/fwlink/?linkid=206015%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=206015&amp;clcid=0x411</a>) を参照してください。


## トポロジ ビルダーを使用して仲介サーバーを構成するには

1.  トポロジ ビルダーで既存のトポロジを開きます。

2.  左ウィンドウで、\[ **PSTN ゲートウェイ** \] に移動します。

3.  \[ **PSTN ゲートウェイ** \] を右クリックし、\[ **新しい IP/PSTN ゲートウェイ** \] をクリックします。

4.  \[ **新しい IP/PSTN ゲートウェイの定義** \] ページに、次の情報を入力します。
    
      - ゲートウェイの FQDN または IP アドレスを入力します。ゲートウェイが TLS プロトコルを使用する場合は、ゲートウェイの FQDN が必要です。
    
      - \[ **IP/PSTN ゲートウェイのリッスン ポート** \] の既定値をそのまま使用するか、変更されている場合は新しいリッスン ポートを入力します。
    
      - \[ **SIP 転送プロトコル** \] を設定します。

5.  左ウィンドウで、\[ **Enterprise Edition フロントエンド プール** \] または \[ **Standard Edition サーバー** \] に移動します。

6.  プールを右クリックし、\[ **プロパティの編集** \] をクリックします。

7.  \[ **仲介サーバー** \] で、\[ **リッスン ポート** \] を設定します。

8.  次に、新しく作成した PSTN ゲートウェイを関連付けます。それには、PSTN ゲートウェイを選択し、\[ **追加** \] をクリックします。

9.  **トポロジ ビルダー** で、最上位ノードの \[ **Lync Server** \] を選択します。

10. \[ **操作** \] メニューの \[ **トポロジの公開** \] を選択し、\[ **次へ** \] をクリックします。

11. **公開ウィザード** の実行が完了したら、\[ **完了** \] をクリックしてウィザードを閉じます。

> [!NOTE]
> 次のトピック「 <a href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync Server 2013 仲介サーバーを使用するようにボイス ルートを変更する</a>」の手順を完了して、音声ルートが正しい仲介サーバーを参照するようにすることが重要です。

