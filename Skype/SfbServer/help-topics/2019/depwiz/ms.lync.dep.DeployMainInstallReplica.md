---
title: ローカル構成ストアのインストール
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: ビジネスのサーバーの役割のサーバーの新しい Skype のインストールを開始するには、最初にローカル構成ストアをホストするローカルの SQL Server をインストールする必要があります。 ローカル構成ストアは、ビジネスのサーバーの中央管理ストア (CMS) の Skype の読み取り専用レプリカとして機能します。
ms.openlocfilehash: ab19a45925a25b97e9b1c478c631ee71fe999b83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993671"
---
# <a name="install-local-configuration-store"></a>ローカル構成ストアのインストール
 
ビジネスのサーバーの役割のサーバーの新しい Skype のインストールを開始するには、最初にローカル構成ストアをホストするローカルの SQL Server をインストールする必要があります。 ローカル構成ストアは、ビジネスのサーバーの中央管理ストア (CMS) の Skype の読み取り専用レプリカとして機能します。 [**ローカル構成ストアのインストール**] 手順を実行しているサーバーに、そのコンピューターのローカル管理者としてログオンすると共に、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーシップを持っている必要があります。 エッジ サーバーでセットアップを実行する場合は、RTCUniversalServerAdmins または RTCUniversalGlobalReadOnlyGroup グループのメンバーでなくても構いません。 トポロジ ビルダー定義ドキュメントの代わりに中央管理ストアからエクスポートした定義ドキュメントから読み取られます。 トポロジ ビルダー定義ドキュメントをエクスポートしてエッジ サーバーを使用できるように、「[トポロジーのエクスポートとコピーして、エッジ インストール用の外部メディア](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)」を参照してください。
  
インストールを開始するには、以下の操作を行います。
  
1. ビジネス サーバー ページの場合は、Skype で横に**ステップ 1: ローカル構成ストアのインストール**を**実行**] をクリックします。
    
2. [**ローカル サーバー構成**] ページで、[**中央管理ストアから直接取得する**] オプションがオンになっていることを確認し、[**次へ**] をクリックします。
    
3. ローカル サーバー構成のインストールが完了したら、[**完了**] をクリックします。
    
> [!NOTE]
> ローカルの SQL Server のインストール時間がかかることができます。 SQL Server のインストール中に [サマリー] 画面でインストールの進行状況の更新は表示されません。 インストールの進行状況を監視する場合は、SQL Server セットアップを監視するタスク マネージャーを使用します。 
  

