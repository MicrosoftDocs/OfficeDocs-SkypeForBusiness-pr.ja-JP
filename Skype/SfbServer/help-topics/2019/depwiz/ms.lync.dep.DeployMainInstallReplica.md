---
title: ローカル構成ストアのインストール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Skype for Business Server 役割サーバーのインストールを開始するには、まずローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management ストア (CMS) の読み取り専用レプリカとして機能します。
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095981"
---
# <a name="install-local-configuration-store"></a>ローカル構成ストアのインストール

新しい Skype for Business Server 役割サーバーのインストールを開始するには、まずローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management ストア (CMS) の読み取り専用レプリカとして機能します。 **[ローカル構成ストアのインストール]** 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントは、中央管理ストアではなく、エクスポートされた定義ドキュメントから読み取されます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、トピック「トポロジのエクスポートとエッジ インストール用の外部メディアへのコピー」を[参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)。

インストールを開始するには、以下の操作を行います。

1. [Skype for Business Server] ページで、[手順 **1:** ローカル構成ストアのインストール] の横にある [実行] を **クリックします**。

2. [**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。

3. ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。

> [!NOTE]
> ローカル アプリケーションのインストールにはSQL Server時間がかかる場合があります。 インストール中にインストールの概要画面に進行状況の更新SQL Server表示されません。 インストールの進行状況を監視する場合は、タスク マネージャーを使用して、インストールのSQL Serverします。