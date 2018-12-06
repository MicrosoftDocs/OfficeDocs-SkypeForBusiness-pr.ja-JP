---
title: 'Lync Server 2013: Standard Edition サーバーのテスト'
TOCTitle: Standard Edition サーバーのテスト
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48273362
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Standard Edition サーバーのテスト

 

_**トピックの最終更新日:** 2012-10-01_

次の手順では、 Standard Edition サーバーの展開をテストする方法について説明します。

## Standard Edition サーバーの展開をテストするには

1.  Active Directory コンピューターとユーザーを使用して、( Lync Server コントロール パネルがインストールされている) Lync Server 2013 展開用の管理者役割である Active Directory ユーザー オブジェクトを **CSAdministrator** グループに追加します。

2.  ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。
    
    > [!NOTE]
    > Lync Server 2013 Standard Edition を実行するサーバーのローカル管理者のユーザー アカウントは使用できません。CsAdministors グループに適切なユーザーとグループを追加しない場合は、 Lync Server 2013 コントロール パネルを開くときに &quot;権限がありません: 役割ベースのアクセス制御 (RBAC) の承認が失敗したため、アクセスが拒否されました&quot; というメッセージが表示され、エラーとなります。


3.  管理者のアカウントを使用して、 Lync Server コントロール パネルがインストールされたコンピューターにログオンします。

4.  Lync Server コントロール パネルを開いて、資格情報の入力を求められたら情報を入力します。 Lync Server 2013 コントロール パネルは展開情報を表示します。

5.  左側のナビゲーション バーで \[**トポロジ**\] をクリックし、サービスの状態は緑の矢印がついたコンピューター アイコンになっていて、展開してオンラインにした各 Lync Server のサーバーの役割の横に緑のチェック マークがあることを確認します。

6.  左側のナビゲーション バーで \[**ユーザー**\] をクリックし、2 人のユーザーを Lync Server 2013 に対して有効にします。

7.  1 人のユーザーがドメインに参加しているコンピューターにログオンし、もう 1 人のユーザーがドメイン内の別のコンピューターにログオンします。

8.  2 台のクライアント コンピューターのそれぞれに Lync Server 2013 をインストールし、両方のユーザーが Lync Server 2013 にサインインできて、相互にインスタント メッセージを送信できることを確認します。

## 関連項目

#### 概念

[Lync Server 2013 でのクライアントおよびデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)

