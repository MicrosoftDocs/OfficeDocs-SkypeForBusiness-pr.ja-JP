---
title: パイロット プールとレガシ プールの共存を確認する
TOCTitle: パイロット プールとレガシ プールの共存を確認する
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48272198
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# パイロット プールとレガシ プールの共存を確認する

 

_**トピックの最終更新日:** 2012-09-28_

## Office Communications Server 2007 R2 管理ツールでプールを確認する

1.  Office Communications Server 2007 R2 管理ツールを開きます。

2.  \[**フォレスト**\] ノード、\[**Standard Edition サーバー**\] ノードまたは \[**エンタープライズ プール**\] ノード、プールまたはサーバー名の順に展開します。

3.  そのプールで Office Communications Server 2007 R2 のサービスが実行されていることを確認します。
    
    ![Office Communications Server 2007 R2 管理コンソール](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理コンソール")  

## Lync Server 2013 コントロール パネルでパイロット プールを確認する

1.  CsAdministrator の役割のメンバーであるユーザー アカウントを使用して、Lync Server 2013 フロントエンド サーバーにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  \[**トポロジ**\] をクリックします。

4.  展開したサーバーがパイロット プール内に存在することを確認します。
    
    ![Lync Server コントロール パネル、\[トポロジ\] ページ](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server コントロール パネル、[トポロジ] ページ")  

## Lync Server 2013 のサービスが開始されていることを確認する

1.  Lync Server 2013 フロントエンド サーバーで、\[**管理ツール**\] グループの \[**サービス**\] アプレットを開きます。

2.  一覧表示されるサービスが次の図の一覧と一致することを確認します。
    
    ![開始された Lync サービスが表示されている \[サービス\] ページ](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "開始された Lync サービスが表示されている [サービス] ページ")

