---
title: Skype for Business Server で AlwaysOn 可用性グループを使用してデータベースを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: 既存の AlwaysOn 可用性グループにさらに Skype for Business Server データベースを追加する方法と、Skype for Business Server の AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用またはアップグレードした後の必要な追加手順について説明します。'
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826367"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Skype for Business Server で AlwaysOn 可用性グループを使用してデータベースを管理する

この記事の手順を使用して、Skype for Business Server の既存の AlwaysOn 可用性グループにさらに Skype for Business Server データベースを追加し、Skype for Business Server の AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用またはアップグレードした後に必要な追加の手順を確認します。

## <a name="add-databases-to-an-alwayson-availability-group"></a>AlwaysOn 可用性グループにデータベースを追加する 

1. このSQL Server Management Studio開き、AlwaysOn 可用性グループに移動します。 プライマリ レプリカにフェールオーバーします。
    
2. トポロジ ビルダーで、AlwaysOn 可用性SQL Serverの FQDN をそのグループのプライマリ ノードの FQDN に設定します。
    
   - トポロジ ビルダーを開き、[既存の展開から **トポロジ** をダウンロードする] を選択し **、[OK] をクリックします**。
    
   - [Skype for Business Server] を展開し、トポロジを展開し、[ストア] **SQL Server展開します**。 新しい AlwaysOn 可用性SQLストアを右クリックし、[プロパティの編集] を **クリックします**。
    
   - ページの下部にある [SQL Server **FQDN]** ボックスに、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。
    
3. トポロジを公開します。 [操作 **] メニューの** [ **トポロジ] をクリックし、[公開]** を **クリックします**。 次に、確認ページで [次へ] を **クリックします**。
    
4. このSQL Server Management Studio使用して、新しいデータベースを AlwaysOn 可用性グループに追加します。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>AlwaysOn 可用性グループのSQL Serverまたは更新する

AlwaysOn 可用性グループの一部であるバック エンド サーバーにパッチを適用した後、トポロジを再公開する必要があります。

1. Skype for Business サーバーに更新プログラムをインストールします。
    
2. Skype for Business 管理シェルで次の PowerShell コマンドを実行します (SQL AlwaysOn データベースに変更を適用するための適切なアクセス許可を持つアカウントでログインします)。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    ここで、[sqlpool.contoso.com] は AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えてください。
