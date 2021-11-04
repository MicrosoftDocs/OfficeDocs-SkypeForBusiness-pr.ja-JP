---
title: ローカル構成ストアのインストール
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 2015 年 2015 年の新しい役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。 Skype for Business Server ローカル構成ストアは、サーバーの全体管理ストア (CMS) のSkype for Business Serverレプリカとして機能します。 [ローカル構成ストアのインストール] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントは、中央管理ストアではなく、エクスポートされた定義ドキュメントから読み取されます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、「トポロジのエクスポート」および「エッジ インストール用に外部メディアにコピーする」を参照してください。
ms.openlocfilehash: 337aa29d895523dd6a255cf1cf542b747b9656df
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770915"
---
# <a name="install-local-configuration-store"></a>ローカル構成ストアのインストール

2015 年 2015 年の新しい役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Serverをインストールする必要があります。 Skype for Business Server ローカル構成ストアは、サーバーの全体管理ストア (CMS) のSkype for Business Serverレプリカとして機能します。 **[ローカル構成ストアのインストール]** 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンするとともに、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントは、中央管理ストアではなく、エクスポートされた定義ドキュメントから読み取されます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーで使用するには、トピック「トポロジのエクスポートとエッジ インストール用の外部メディアへのコピー」を [参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)。

インストールを開始するには、以下の操作を行います。

1. [2015 Skype for Business Server] ページで、[手順 **1:** ローカル構成ストアのインストール] の横にある [実行] を **クリックします**。

2. [**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。

3. ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。

> [!NOTE]
> ローカル アプリケーションのインストールにはSQL Server時間がかかる場合があります。 インストール中にインストールの概要画面に進行状況の更新SQL Server表示されません。 インストールの進行状況を監視する場合は、タスク マネージャーを使用して、インストールのSQL Serverします。