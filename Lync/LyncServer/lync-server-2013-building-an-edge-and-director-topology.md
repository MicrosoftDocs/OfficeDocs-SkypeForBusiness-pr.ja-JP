---
title: 'Lync Server 2013: エッジおよびディレクターのトポロジの作成'
TOCTitle: エッジおよびディレクターのトポロジの作成
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48271311
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのエッジおよびディレクターのトポロジの作成

 

_**トピックの最終更新日:** 2012-09-08_

トポロジの構築には、次の計画タスクと展開タスクが含まれます。

  - **計画**   組織に適合するトポロジを定義して、その展開に必要なコンポーネントを特定する必要があります。これらは、計画プロセスの標準的なステップです。Microsoft Lync Server 2013 で提供される Lync Server 2013計画ツールを使用すると、計画プロセスを容易に開始でき、要件と計画が完成した時点で簡単に変更もできます。

  - **展開**    Lync Server 2013 サーバーの展開には、トポロジ ビルダーを使用して定義したトポロジが不可欠です。計画タスクの一環として トポロジ ビルダーを使用してトポロジの定義と公開を完了していない場合は、それを完了し、トポロジを公開してから、エッジ サーバーを展開する必要があります。

少なくとも 1 つの内部プールを展開するまではエッジ サーバーのコンポーネントは展開できません。また、内部プールの展開には トポロジ ビルダーをインストールする必要があります。 ここでは、トポロジ ビルダーのインストールについては説明しません。このインストールは、内部プールのインストール プロセスに含まれるからです。

これらのツールの詳細については、「[Lync Server 2013 の外部ユーザー アクセスの展開チェックリスト](lync-server-2013-deployment-checklist-for-external-user-access.md)」を参照してください。

> [!NOTE]
> 以前に トポロジ ビルダーを使用して、エッジ トポロジを含む完全なトポロジを定義した場合は、このセクションの「<a href="lync-server-2013-define-your-edge-topology.md">Lync Server 2013 でエッジ トポロジを定義する</a>」タスクおよび「<a href="lync-server-2013-publish-your-topology.md">Lync Server 2013 でのトポロジの公開</a>」タスクは省略できますが、「<a href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする</a>」タスクは完了する必要があります。


## このセクション中

  - [Lync Server 2013 でエッジ トポロジを定義する](lync-server-2013-define-your-edge-topology.md)

  - [Lync Server 2013 のトポロジにオプションのディレクター トポロジを定義する](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [Lync Server 2013 でのトポロジの公開](lync-server-2013-publish-your-topology.md)

  - [エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

