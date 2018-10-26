---
title: 'Lync Server 2013: トポロジの定義と構成'
TOCTitle: トポロジの定義と構成
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48272081
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのトポロジの定義と構成

 

_**トピックの最終更新日:** 2012-09-14_

トポロジ ビルダーを使用すると、トポロジを定義および構成することができます。トポロジ ビルダーでは、ローカルの Administrators グループまたは特権ドメイン グループ (Domain Admins など) のメンバーである必要はありません。 標準ユーザーでもトポロジを定義できます。 初めて トポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。 選択肢には以下があります。

  - 既存の展開環境からトポロジをダウンロードする

  - ローカル ファイルからトポロジを開く

  - 新しいトポロジ

既にトポロジを定義していて、中央管理ストアを確立してある場合、既存の展開環境からトポロジをダウンロードする必要があります。トポロジ ビルダーはデータストアを読み取って、現在の定義を取得します。 既存の 中央管理ストアがある場合は、必ずこのオプションを選択します。

中央管理ストアを確立していなくて、以前保存した構成を編集する場合は、トポロジをローカル ファイルから開く必要があります。 開くファイルは、以前のセッションで保存した構成ファイルになります。 このオプションを使用して、以前保存されたトポロジを編集することができます。


> [!WARNING]
> トポロジを既に公開している場合は、ローカル構成ファイルを読み込まないでください。 既存の展開環境からトポロジをダウンロードする必要があります。



新しい トポロジ ビルダーの構成を作成する場合は、新しいトポロジを作成します。 以前の設計セッションで作成したものと同じファイルとして保存しなければ、以前保存した設計は上書きされません。

これらの各オプションで、トポロジ ビルダーの構成ファイルの保存場所を指定するように指示されます。 ファイルの場所は、ローカルの場所、確立されたファイル共有の共有の場所、またはリムーバブル メディアにすることができます。

## このセクション中

  - [Lync Server 2013 のトポロジ ビルダーでのトポロジの定義と構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 での障害復旧用のペアのフロント エンド プールの展開](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Lync Server 2013 での簡単な URL の編集または構成](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Lync Server 2013 での中央管理サーバーの選択](lync-server-2013-select-the-central-management-server.md)

