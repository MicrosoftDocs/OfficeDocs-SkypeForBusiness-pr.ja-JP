---
title: ローカル構成ストアのインストール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 新しい Skype for Business Server の役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Server をインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management store (CMS) の読み取り専用レプリカとして機能します。
ms.openlocfilehash: 699294889008f0d353e1ba727cbc078f9616f4ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303405"
---
# <a name="install-local-configuration-store"></a>ローカル構成ストアのインストール

新しい Skype for Business Server の役割サーバーのインストールを開始するには、まず、ローカル構成ストアをホストするローカル SQL Server をインストールする必要があります。 ローカル構成ストアは、Skype for Business Server Central Management store (CMS) の読み取り専用レプリカとして機能します。 [**ローカル構成ストアのインストール**] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンすると共に、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジビルダー定義ドキュメントは、中央管理ストアからではなく、エクスポートされた定義ドキュメントから読み取ります。 トポロジビルダーの定義ドキュメントをエクスポートして、エッジサーバーで利用できるようにするには、「[トポロジをエクスポートして、edge のインストール用に外部メディアにコピー](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)する」のトピックを参照してください。

インストールを開始するには、以下の操作を行います。

1. [Skype for Business Server] ページで、[**ステップ 2: ローカル構成ストアをインストール**します] の横にある [**実行**] をクリックします。

2. [**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。

3. ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。

> [!NOTE]
> ローカル SQL Server のインストールには時間がかかることがあります。 SQL Server がインストールされている間、インストールの概要画面の [更新の進行状況] は表示されません。 インストールの進行状況を監視する場合は、タスクマネージャーを使って SQL Server のセットアップを確認します。


