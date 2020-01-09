---
title: Skype for Business Server の AlwaysOn 可用性グループでデータベースを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: Skype for Business Server データベースを既存の AlwaysOn 可用性グループに追加する方法について説明し、Skype for the AlwaysOn 可用性グループの一部であるバックエンドサーバーを修正またはアップグレードした後に必要な追加の手順について説明します。Business Server。'
ms.openlocfilehash: 221964eb7d8dfcbb0303a0e1148de4fcef6cec51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991542"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Skype for Business Server の AlwaysOn 可用性グループでデータベースを管理する

この記事の手順を使用して、Skype for Business Server の既存の AlwaysOn 可用性グループにさらに Skype for Business Server データベースを追加します。 AlwaysOn の一部であるバックエンドサーバーを修正またはアップグレードした後で、必要な追加の手順を確認してください。Skype for Business Server の可用性グループ。

## <a name="add-databases-to-an-alwayson-availability-group"></a>AlwaysOn 可用性グループにデータベースを追加する 

1. SQL Server Management Studio を開き、AlwaysOn 可用性グループに移動します。 プライマリレプリカにフェイルオーバーします。
    
2. [トポロジビルダー] で、AlwaysOn 可用性グループの SQL Server FQDN をそのグループのプライマリノードの FQDN に設定します。
    
   - トポロジビルダーを開き、[**既存の展開からトポロジをダウンロード**] を選択して、[ **OK]** をクリックします。
    
   - [Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。 新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[プロパティの**編集**] をクリックします。
    
   - ページの下部にある [ **SQL SERVER FQDN** ] ボックスに、AlwaysOn 可用性グループのプライマリノードの FQDN を入力します。
    
3. トポロジを公開します。 [**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。 続いて、確認ページで [**次へ**] をクリックします。
    
4. SQL Server Management Studio を使用して、新しいデータベースを AlwaysOn 可用性グループに追加します。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>AlwaysOn 可用性グループの SQL Server に対して修正プログラムを適用または更新を実行する

AlwaysOn 可用性グループの一部であるバックエンドサーバーを更新した後、トポロジを再公開する必要があります。

1. Skype for Business Server に更新プログラムをインストールします。
    
2. Skype for Business 管理シェルで次の PowerShell コマンドを (SQL AlwaysOn データベースに変更を適用する適切な権限を持ったアカウントでログインした上で) 次のとおり実行します。
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    [sqlpool.contoso.com] は、AlwaysOn 可用性グループの完全修飾ドメイン名 (FQDN) に置き換えられます。
