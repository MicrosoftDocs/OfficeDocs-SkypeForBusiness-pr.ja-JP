---
title: 'Lync Server 2013: スキーマのレプリケーションの確認'
TOCTitle: スキーマのレプリケーションの確認
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48273253
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Active Directory スキーマのレプリケーションの確認

 

_**トピックの最終更新日:** 2012-10-29_

フォレストの準備を実行する前に、スキーマ パーティションがレプリケートされたことを手動で確認してください。

## スキーマのレプリケーションを手動で確認するには

1.  Enterprise Admins グループのメンバーとしてドメイン コントローラーにログオンします。

2.  \[**スタート**\] をクリックして \[**管理ツール**\] をクリックし、\[**ADSI エディター**\] をクリックして ADSI エディターを開きます。
    

    > [!TIP]
    > または、コマンド ラインから <STRONG>adsiedit.msc</STRONG> を実行することもできます。



3.  Microsoft 管理コンソール (MMC) ツリーで、まだ選択されていない場合には \[**ADSI エディター**\] をクリックします。

4.  \[**アクション**\] メニューで、\[**接続**\] をクリックします。

5.  \[**接続の設定**\] ダイアログ ボックスの \[**既知の名前付けコンテキストを選択する**\] で、\[**スキーマ**\] を選択して \[**OK**\] をクリックします。

6.  スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。

## 関連項目

#### タスク

[Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)  

#### 概念

[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)

