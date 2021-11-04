---
title: AlwaysOn 可用性グループを使用してデータベースを管理Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: 既存の AlwaysOn 可用性グループに Skype for Business Server データベースを追加する方法と、Skype for Business Server の AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用またはアップグレードした後に必要な追加手順について説明します。'
ms.openlocfilehash: c47d5833b7569faa424415b1e5b7315bab4d4aae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756994"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>AlwaysOn 可用性グループを使用してデータベースを管理Skype for Business Server

この記事の手順を使用して、Skype for Business Server の既存の AlwaysOn 可用性グループに Skype for Business Server データベースを追加し、Skype for Business Server の AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用またはアップグレードした後に必要な追加手順について説明します。

## <a name="add-databases-to-an-alwayson-availability-group"></a>AlwaysOn 可用性グループにデータベースを追加する 

1. [SQL Server Management Studio開き、AlwaysOn 可用性グループに移動します。 プライマリ レプリカにフェールオーバーします。
    
2. トポロジ ビルダーで、AlwaysOn 可用性SQL Serverの FQDN を、そのグループのプライマリ ノードの FQDN に設定します。
    
   - [トポロジ ビルダー] を開き、[ **既存の** 展開からトポロジをダウンロードする] を選択し **、[OK] をクリックします**。
    
   - [Skype for Business Server] を展開し、トポロジを展開し、[ストア] **SQL Server展開します**。 新しい AlwaysOn 可用性グループのSQLを右クリックし、[プロパティの編集]**をクリックします**。
    
   - ページの下部の **[FQDN]** ボックスSQL Server AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。
    
3. トポロジを公開します。 [操作] **メニューの [** トポロジ] **をクリックし** 、[発行] **をクリックします**。 次に、確認ページで [次へ] を **クリックします**。
    
4. AlwaysOn 可用性SQL Server Management Studioに新しいデータベースを追加するには、次の情報を使用します。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>AlwaysOn 可用性グループのSQL Server更新または修正する

AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用した後、トポロジを再発行する必要があります。

1. 更新プログラムをサーバーまたはサーバー Skype for Businessインストールします。
    
2. Skype for Business 管理シェルで次の PowerShell コマンドを実行します (SQL AlwaysOn データベースに変更を適用するための適切な権限を持つアカウントでログインします)。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    [sqlpool.contoso.com] が AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられる場合。
