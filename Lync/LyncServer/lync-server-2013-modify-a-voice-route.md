---
title: Lync Server 2013 でのボイス ルートの変更
TOCTitle: Lync Server 2013 でのボイス ルートの変更
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48273279
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのボイス ルートの変更

 

_**トピックの最終更新日:** 2016-12-08_

ここでは、ボイス ルートを編集する方法について説明します。 新しいルートを作成するには、「[Lync Server 2013 でのボイス ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。

## ボイス ルートを変更するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ボイス ルート**\] をクリックし、\[**ルート**\] をクリックします。

4.  \[**ルート**\] ページで、次のいずれかの方法を使用してボイス ルートを変更します。
    
      - ボイス ルート名をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。
    
      - ボイス ルート名をクリックし、\[**編集**\] をクリックし、\[**コピー**\] をクリックしてから、\[**貼り付け**\] をクリックします。 直前に作成したボイス ルートの新しいコピーをクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。

5.  \[**ボイス ルートの編集**\] ページの \[**名前**\] フィールドに、ボイス ルートのわかりやすい名前を入力します。

6.  (オプション) \[**説明**\] フィールドに、ボイス ルートのわかりやすい追加情報を入力します。

7.  このルートが対応するパターンを指定するには、**一致パターン構築**ツールを使用して正規表現を生成するか、手動で正規表現を記述します。
    
      - **一致パターン構築**ツールを使用して正規表現を生成するには、次の値を入力します。 次の 2 種類の一致するパターンを指定できます。
        
          - **許可する番号の開始番号:** このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。 たとえば、「**+425**」と入力して、\[**追加**\] をクリックします。 このルートに含める各プレフィックス値について、この手順を繰り返します。
        
          - **例外:** プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、\[**例外**\] をクリックします。 このルートが対応しない一致パターンの値を 1 つまたは複数入力します。 たとえば、ルートから +425237 で始まる番号を除外するには、\[**例外**\] フィールドに「**+425237**」と入力して、\[**OK**\] をクリックします。
    
      - 一致パターンを手動で定義するには、**一致パターン構築**ツールの \[**編集**\] をクリックし, .NET Framework 正規表現を入力して、ルートが適用される相手電話番号の一致パターンを指定します。正規表現の記述方法については、「.NET Framework の正規表現」([http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x411)) を参照してください。

8.  通話を発信する電話の ID を呼び出し先に表示しない場合は、\[**発信者番号を表示しない** \] を選択します。このオプションを選択した場合、呼び出し先の発信者 ID 表示に表示される、\[**代替発信者番号**\] を指定する必要があります。

9.  1 つまたは複数の公衆交換電話網 (PSTN) トランクをボイス ルートに関連付けるには、\[**追加**\] をクリックして、一覧からトランクを選択します。
    
    > [!NOTE]
    > 展開に Microsoft Office Communications Server 2007 R2 仲介サーバーが含まれる場合、これらのサーバーも一覧で選択できます。


10. 1 つまたは複数の PSTN 使用法をボイス ルートに関連付けるには、\[**選択**\] をクリックして、エンタープライズ VoIP 展開で定義済みの PSTN 使用法レコードの一覧からレコードを選択します。
    
    > [!NOTE]  
    > 選択できる PSTN 使用法レコードの各プロパティを表示するには、「<a href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013 での PSTN 使用法レコードの表示</a>」を参照してください。<br />
    > PSTN 使用法レコードを作成または編集するには、「<a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成</a>」または「<a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</a>」を参照してください。


11. 最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。
    
    > [!NOTE]
    > 一覧表示される PSTN 使用法レコードの順番が重要である音声ポリシーとは異なり、ボイス ルートでの順番は重要ではありません。 ただし、この一覧を使用頻度で整理することをお勧めします。例: &quot;レドモンド市内&quot;、&quot;レドモンド長距離&quot;、&quot;レドモンド国際&quot;、&quot;レドモンド バックアップ&quot; の順に並べます。 (Lync Server はこの一覧を上から下に検索します。)


12. (オプション) \[**テストする変換後の番号の入力**\] フィールドに値を入力して、\[**実行**\] をクリックします。 テスト結果がフィールドの下に表示されます。
    
    > [!NOTE]
    > まだテストに成功していないボイス ルートを保存して、後で再構成することができます。詳細については、「<a href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</a>」を参照してください。


13. \[**OK**\] をクリックします。

14. \[**ルート**\] ページの \[**確定**\] をクリックして、\[**すべて確定**\] をクリックします。
    
    > [!NOTE]
    > 音声ルートを作成または変更するときは常に、[<strong>すべて確定</strong>] コマンドを実行して、構成の変更を公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 でのボイス ルートの作成](lync-server-2013-create-a-voice-route.md)  
[Lync Server 2013 での PSTN 使用法レコードの表示](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### その他のリソース

[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

