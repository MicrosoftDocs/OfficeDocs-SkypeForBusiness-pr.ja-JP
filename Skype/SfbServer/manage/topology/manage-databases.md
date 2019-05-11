---
title: ビジネス サーバーの Skype での AlwaysOn 可用性グループにデータベースを管理します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: ビジネス サーバー データベースの複数の Skype を既存の AlwaysOn 可用性グループに追加、修正した後、必要な追加手順の詳細についてや、バック エンド サーバーの Skype での AlwaysOn 可用性グループの一部であるをアップグレードする方法を学習します。ビジネス サーバーです。'
ms.openlocfilehash: 07aaadc303063204cef4a5561a83ec71b629c21b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911932"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>ビジネス サーバーの Skype での AlwaysOn 可用性グループにデータベースを管理します。

この資料の手順を使用して、ビジネスのサーバーの Skype で既存の AlwaysOn 可用性グループにビジネス サーバー データベースの複数の Skype を追加し、修正プログラムを適用または、バック エンド サーバー、AlwaysOn の一部をアップグレードした後、必要な追加手順をお探しSkype ビジネス サーバーの可用性グループです。

## <a name="add-databases-to-an-alwayson-availability-group"></a>データベースを AlwaysOn 可用性グループに追加します。 

1. SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。 フェールオーバー、プライマリ レプリカにします。
    
2. トポロジ ビルダーでは、AlwaysOn 可用性グループの SQL Server の FQDN をそのグループのプライマリ ノードの FQDN に設定します。
    
   - トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して **[ok]** をクリックします。
    
   - [Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。 新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。
    
   - **SQL Server の FQDN** ] ボックスで、ページの下部に、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。
    
3. トポロジを公開します。 [**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。 続いて、確認ページで [**次へ**] をクリックします。
    
4. AlwaysOn 可用性グループに新しいデータベースを追加するのにには、SQL Server Management Studio を使用します。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>AlwaysOn 可用性グループの SQL Server に対して修正プログラムを適用または更新を実行する

バック エンド サーバー、AlwaysOn 可用性グループの一部を修正するには後に、、トポロジを再発行する必要があります。

1. Skype for Business Server に更新プログラムをインストールします。
    
2. Skype for Business 管理シェルで次の PowerShell コマンドを (SQL AlwaysOn データベースに変更を適用する適切な権限を持ったアカウントでログインした上で) 次のとおり実行します。
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    [sqlpool.contoso.com] は、AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられます。
