---
title: エンタープライズ VoIP に対するユーザーの無効化
TOCTitle: エンタープライズ VoIP に対するユーザーの無効化
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49886937
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# エンタープライズ VoIP に対するユーザーの無効化

 

_**トピックの最終更新日:** 2012-09-21_

次の手順を使用して、Lync Server 2013 に対して有効になっているユーザー アカウントに対して エンタープライズ VoIP を無効にします。

## エンタープライズ VoIP のユーザー アカウントを無効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  \[**ユーザーの検索**\] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、\[**検索**\] をクリックします。

5.  表で、エンタープライズ VoIP に対して有効にするユーザー アカウントをクリックします。

6.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

7.  \[**Lync Server ユーザーの編集**\] ページの \[**テレフォニー**\] で、\[**エンタープライズ VoIP**\] 以外のオプションをクリックします。
    
    > [!NOTE]
    > ユーザーが Lync を使用して音声通話やビデオ通話を行えないようにするには、[<strong>テレフォニー</strong>] で [<strong>音声ビデオを無効にする</strong>] をクリックします。


8.  \[**確定**\] をクリックします。

ユーザーは、エンタープライズ VoIP 機能を使用できなくなりました。

## 関連項目

#### タスク

[Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)  

#### その他のリソース

[ユーザーのエンタープライズ VoIP の管理](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)

