---
title: 手動による変換ルールの作成または変更
TOCTitle: 手動による変換ルールの作成または変更
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48271105
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 手動による変換ルールの作成または変更

 

_**トピックの最終更新日:** 2012-08-06_

一致するパターンおよび変換ルールの正規表現を書いて変換ルールを定義する場合は、次の手順を実行します。また、**変換ルールの作成**ツールに一連の値を入力して、Lync Server コントロール パネルで対応する一致パターンと変換ルールを生成できるようにすることもできます。詳細については、「[変換ルールの構築ツールを使用した変換ルールの作成または変更](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)」を参照してください。

## 変換ルールを手動で定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  変換ルールの定義を開始するには、「[Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)」の手順 10 まで、または「[Lync Server 2013 でメディア バイパスを無効にしてトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)」の手順 9 までの手順に従います。

4.  \[**新しい変換ルール**\] ページまたは \[**変換ルールの編集**\] ページの \[**名前**\] フィールドに、変換対象の番号パターンを説明する名前を入力します。

5.  (省略可能) \[**説明**\] に、「**米国長距離国際電話ダイヤル**」など、変換ルールの説明を入力します。

6.  \[**変換ルールの構築**\] セクションの一番下にある \[**編集**\] をクリックします。

7.  \[**正規表現の入力**\] に、次のように入力します。
    
      - \[**このパターンと一致**\] に、変換する番号を照合するために使用するパターンを指定します。
    
      - \[**変換ルール**\] に、変換される番号の形式のパターンを指定します。
    
    たとえば、\[**このパターンと一致**\] には「**^\\+(\\d{9}\\d+)$**」、\[**変換ルール**\] には「**011$1**」と入力すると、ルールにより +441235551010 が 011441235551010 に変換されます。

8.  \[**OK**\] をクリックして変換ルールを保存します。

9.  \[**OK**\] をクリックしてトランク構成を保存します。

10. \[**トランク構成**\] ページで \[**確定**\] をクリックして、\[**すべて確定**\] をクリックします。
    
    > [!NOTE]
    > 変換ルールを作成または変更したときはかならず、[<strong>すべて確定</strong>] コマンドを実行して構成の変更を公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。


## 関連項目

#### タスク

[変換ルールの構築ツールを使用した変換ルールの作成または変更](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でメディア バイパスを無効にしてトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### 概念

[Lync Server 2013 でのグローバル メディア バイパス オプション](lync-server-2013-global-media-bypass-options.md)

