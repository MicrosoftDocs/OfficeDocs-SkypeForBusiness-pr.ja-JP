---
title: Lync Server 2013 でのボイス ルートの作成
TOCTitle: Lync Server 2013 でのボイス ルートの作成
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48273647
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのボイス ルートの作成

 

_**トピックの最終更新日:** 2016-12-08_

次の手順では、Lync Server 2013 コントロール パネルを使って新しい音声ルートを作成する方法について説明します。既存のルートを編集するには、「[Lync Server 2013 でのボイス ルートの変更](lync-server-2013-modify-a-voice-route.md)」の手順を参照してください。

## Lync Server コントロール パネルを使用して音声ルートを作成するには

1.  RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声ルーティング**\] をクリックします。

4.  \[**ルート**\] をクリックします。

5.  \[**新規**\] をクリックして、\[**新規音声ルート**\] ダイアログ ボックスを表示します。

6.  \[**名前**\] に、音声ルートのわかりやすい名前を入力します。

7.  (オプション) \[**説明**\] に、音声ルートのわかりやすい追加情報を入力します。

8.  このルートが対応するパターンを指定するには、**照合するパターンの作成**ツールを使用して正規表現を生成するか、手動で正規表現を記述します。
    
      - **照合するパターンの作成**ツールを使用して正規表現を生成するには、次の値を入力します。次の 2 種類の照合パターンを指定できます。
        
          - **許可する番号の開始番号:** このルートが対応する必要のあるプレフィックス値を入力します (必要に応じて先頭に + を付けます)。たとえば、「**+425**」と入力して、\[**追加**\] をクリックします。このルートに含める各プレフィックス値について、この手順を繰り返します。
        
          - **例外:** プレフィックス値に 1 つまたは複数の例外を指定する場合、そのプレフィックスをハイライトして、\[**例外**\] をクリックします。このルートが対応しない照合パターンの値を 1 つまたは複数入力します。たとえば、ルートから +425237 で始まる番号を除外するには、\[**例外**\] フィールドに「**+425237**」と入力して、\[**OK**\] をクリックします。
    
      - 照合パターンを手動で定義するには、**照合するパターンの作成**ツールの \[**編集**\] をクリックし, .NET Framework 正規表現を入力して、ルートが適用される相手電話番号の照合パターンを指定します。正規表現の記述方法の詳細については、「.NET Framework の正規表現」([http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x411)) を参照してください。

9.  通話を発信する電話の ID を呼び出し先に表示しない場合は、\[**発信者番号を表示しない**\] を選択します。このオプションを選択した場合、呼び出し先の発信者 ID 表示に表示される、\[**代替発信者番号**\] を指定する必要があります。

10. 1 つまたは複数のトランクを音声ルートに関連付けるには、\[**追加**\] をクリックして、一覧からトランクを選択します。
    
    > [!NOTE]
    > 展開に Microsoft Office Communications Server 2007 R2 仲介サーバーが含まれる場合、これらのサーバーも一覧で選択できます。


11. 1 つまたは複数の公衆交換電話網 (PSTN) 使用法を音声ルートに関連付けるには、\[**選択**\] をクリックして、エンタープライズ VoIP 展開用に定義されている PSTN 使用法レコードの一覧からレコードを選択します。
    
    > [!NOTE]  
    > 選択できる PSTN 使用法レコードの各プロパティを表示するには、「<a href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013 での PSTN 使用法レコードの表示</a>」を参照してください。<br />
    > PSTN 使用法レコードを作成または編集するには、「<a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成</a>」または「<a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコー ドの構成</a>」を参照してください。


12. 最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。
    
    > [!NOTE]
    > 一覧表示される PSTN 使用法レコードの順番が重要である音声ポリシーとは異なり、音声ルートに一覧表示される PSTN 使用法レコードの順番は重要ではありません。ただし、この一覧を使用頻度で整理することをお勧めします。たとえば、&quot;レドモンド市内&quot;、&quot;レドモンド長距離&quot;、&quot;レドモンド国際&quot;、&quot;レドモンド バックアップ&quot; の順に並べます (Lync Server はこの一覧を上から下に検索します)。


13. (オプション) \[**テストする変換後の番号**\] フィールドに値を入力して、\[**実行**\] をクリックします。テスト結果がフィールドの下に表示されます。
    
    > [!NOTE]
    > まだテストに成功していない音声ルートを保存して、後で再構成することができます。詳細については、「<a href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</a>」を参照してください。


14. \[**OK**\] をクリックして音声ルートを保存します。


> [!IMPORTANT]
> 音声ルートを作成したときは毎回、[<STRONG>すべてコミット</STRONG>] コマンドを実行して構成の変更を公開する必要があります。詳細については、「<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。



## 関連項目

#### タスク

[Lync Server 2013 でのボイス ルートの変更](lync-server-2013-modify-a-voice-route.md)  
[Lync Server 2013 での PSTN 使用法レコードの表示](lync-server-2013-view-pstn-usage-records.md)  
[Lync Server 2013 での音声ポリシーの作成と PSTN 使用法レコードの構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### その他のリソース

[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

