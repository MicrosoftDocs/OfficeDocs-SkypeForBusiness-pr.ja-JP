---
title: 'Lync Server 2013: 手動による正規化ルールの作成または変更'
TOCTitle: 手動による正規化ルールの作成または変更
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48274197
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での手動による正規化ルールの作成または変更

 

_**トピックの最終更新日:** 2012-09-22_

正規化ルールを手動で作成または変更する場合は、次の手順を実行します。 Lync Server コントロール パネルの \[正規化ルールの構築\] を使用することによって正規化ルールを作成または変更する場合は、「[Lync Server 2013 での正規化ルールの構築を使用した正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)」を参照してください。

## 正規化ルールを手動で定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  (オプション) 「[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)」または「[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)」の手順に従います。

4.  \[**新しい正規化ルール**\] または \[**正規化ルールの編集**\] の \[**名前**\] に、正規化される番号のパターンについてわかりやすい名前を入力します (たとえば、正規化ルールに「**5DigitExtension** 」という名前を付けます)。

5.  (オプション) \[**説明**\] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。

6.  \[**正規化ルールの構築**\] で \[**編集**\] をクリックします。

7.  \[**正規表現の入力**\] で次のように入力します。
    
      - \[**このパターンを照合**\] で、ダイヤル電話番号を照合するために使用するパターンを指定します。
    
      - \[**変換ルール**\] で、変換される E.164 電話番号の形式のパターンを指定します。
    
    たとえば、\[**このパターンを照合**\] に「**^(\\d{7})$** 」と入力し、\[**変換ルール**\] に「**+1425$1** 」と入力すると、ルールにより 5550100 が正規化されて +14255550100 になります。

8.  (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、\[**内線番号**\] を選択します。

9.  (オプション) 正規化ルールをテストする番号を入力し、\[**次へ**\] をクリックします。テスト結果は、\[**テストする番号の入力**\] の下に表示されます。
    
    > [!NOTE]
    > テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。詳細については、「<a href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</a>」を参照してください。


10. \[**OK**\] をクリックして正規化ルールを保存します。

11. \[**OK**\] をクリックしてダイヤル プランを保存します。

12. \[**ダイヤル プラン**\] ページで \[**確定**\] をクリックして、\[**すべて確定**\] をクリックします。
    
    > [!NOTE]
    > 正規化ルールを作成または変更するときにはいつでも、[<strong>すべて確定</strong>] コマンドを実行して構成の変更を公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 での正規化ルールの構築を使用した正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### その他のリソース

[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

