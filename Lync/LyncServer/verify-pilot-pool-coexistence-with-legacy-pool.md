---
title: パイロット プールとレガシ プールの共存を確認する
TOCTitle: パイロット プールとレガシ プールの共存を確認する
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48274168
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# パイロット プールとレガシ プールの共存を確認する

 

_**トピックの最終更新日:** 2012-09-29_

パイロット プールを展開した後、プール情報を表示するための管理ツールを使用して、2 つのプールの共存を確認する必要があります。Lync Server 2013 プールおよびレガシ プールには、Lync Server 2013 コントロール パネルおよびトポロジ ビルダー ツールを使用する必要があります。

## Lync Server 2013 サービスが開始していることを確認する

1.  Lync Server 2013 フロントエンド サーバーから、管理者ツール\\サービス アプレットに移動します。

2.  次のサービスがフロントエンド サーバーで実行されていることを確認します。

**Lync Server 2013 サービス**

![開始された Lync Server サービスの一覧](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "開始された Lync Server サービスの一覧")

## Lync Server 2013 コントロール パネルを開く

Lync Server 2013 展開のフロントエンド サーバーから Lync Server 2013 コントロール パネルを開き、Lync Server 2010 プールを選択します。同じ手順で Lync Server 2013 プールを開きます。

**Lync Server 2013 コントロール パネルを開く**

![\[URL の選択\] ダイアログ ボックス](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "[URL の選択] ダイアログ ボックス")


> [!IMPORTANT]
> Lync Server コントロール パネル を使用する前に、Lync Server 2013 で Silverlight を Silverlight バージョン 5 にアップグレードする必要があります。



現在、このトポロジには Lync Server 2010 および Lync Server 2013 のサーバーの役割が含まれています。

**Lync Server 2013 コントロール パネルの \[トポロジ\] ページ**

![Lync Server コントロール パネル - \[トポロジ\] ページ](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server コントロール パネル - [トポロジ] ページ")

## Lync Server 2010 トポロジ ビルダーでトポロジを開こうとしない

Lync Server 2010 トポロジ ビルダーを使用してトポロジを開こうとすると、以下のエラーに遭遇する場合があります。トポロジは、Lync Server 2013 トポロジ ビルダーを使用することでのみ表示できます。Lync Server 2013 および Lync Server 2010 両方のプールの作成に Lync Server 2013 トポロジ ビルダーを使用する必要があります。

**Lync Server 2010 トポロジ ビルダーのエラー メッセージ**

![Lync Server トポロジ ビルダー、MMC スナップ エラー](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server トポロジ ビルダー、MMC スナップ エラー")

