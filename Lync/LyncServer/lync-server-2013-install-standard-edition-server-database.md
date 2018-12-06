---
title: 'Lync Server 2013: Standard Edition サーバー データベースのインストール'
TOCTitle: Standard Edition サーバー データベースのインストール
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48271249
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Standard Edition サーバー データベースのインストール

 

_**トピックの最終更新日:** 2012-10-01_

インフラストラクチャ内でユーザーが所属する唯一のサーバーとして Standard Edition サーバーをセットアップする場合、他のサーバー インストールとは異なり、**展開ウィザード**で最初のサーバーのセットアップに特有の選択を行います。

## Standard Edition サーバーをインストールするには

1.  Standard Edition サーバー をインストールするサーバーにローカル管理者または同等のドメインとしてログオンします。

2.  nm-ad-1st Active Directory ドメイン サービスLync Server 用の Active Directory ドメイン サービスの準備 [Lync Server 2013 用の Active Directory ドメイン サービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)

3.  Lync Server 展開ウィザードで、\[ **最初の Standard Edition サーバーの準備**\] をクリックします。

4.  \[**単一の Standard Edition サーバーの準備**\] ページで、\[**次へ**\] をクリックします。

5.  \[**コマンドを実行しています**\] ページで、SQL Server 2012 Express が 中央管理ストアとしてインストールされます。必要なファイアウォール規則が作成されます。データベースと必要なソフトウェアのインストールが完了したら、\[**完了**\] をクリックします。
    
    > [!NOTE]
    > 最初のインストールには少し時間がかかります。この際、コマンド出力の概要画面が更新されることはありません。これは、SQL Server Express がインストールされるためです。データベースのインストールの進行状況を監視する必要がある場合は、タスク マネージャーを使用してセットアップを監視してください。


6.  管理ツールをインストールしていない場合は、\[ Lync Server 展開ウィザード\] ページで \[**トポロジ ビルダーのインストール**\] をクリックします。詳細については、「[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。

7.  \[Active Directory の準備\]、\[最初の Standard Edition サーバーの準備\]、および \[トポロジ ビルダーのインストール\] の横に緑のチェック マークが付いていることを確認します。

