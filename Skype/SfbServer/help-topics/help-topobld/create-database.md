---
title: データベースの作成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: トポロジビルダーを使用すると、SQL Server ストアにデータベースをインストールすることができます。 トポロジビルダーを使用してデータベースをインストールする場合、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。 トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと、CsDatabase コマンドレットを使用する必要があります。
ms.openlocfilehash: cd3bd6e24f0dc3ec21c5cfa8626d9696454855e7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820239"
---
# <a name="create-database"></a>データベースの作成
 
トポロジビルダーを使用すると、SQL Server ストアにデータベースをインストールすることができます。 トポロジビルダーを使用してデータベースをインストールする場合、アプリケーションはトポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースをインストールします。 トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。 特定のコンピューターに特定のデータベースをインストールする必要がある場合、または併置されたデータベースをインストールする必要がある場合は、代わりに Windows PowerShell コマンドラインインターフェイスと、 [CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps)コマンドレットを使用する必要があります。
  
### <a name="creating-a-database"></a>データベースの作成

1. [Skype for Business Server 2015] ノードをクリックし、[**データベースのインストール**] をクリックします。
    
2. [データベースの**インストール**] ダイアログボックスの [**データベースの作成**] ページで、新しいデータベースを作成する SQL Server ストアの完全修飾ドメイン名 (FQDN) を選びます。
    
3. [**詳細設定**] をクリックします。[**データベース ファイルの場所の選択**] ダイアログ ボックスで、次のどちらかのオプションを選択します。
    
   - [**データベース ファイルの場所を自動的に判断する**]。このオプションを選択すると、トポロジ ビルダーは、組み込みのアルゴリズムを使用して、データベースのログ ファイルとデータ ファイルの格納場所を選択します。
    
   - [**既定の SQL Server インスタンスを使用する**]。 このオプションを選択すると、データベースのログ ファイルとデータ ファイルの格納場所を選択するために、組み込みのアルゴリズムは使用されません。 代わりに、ログとデータファイルは、SQL Server の既定のパスで指定した場所に保存されます (これらのパスは、SQL Server 管理者が advanced で構成する必要があります)。 データ ファイルは SQL Server の既定のデータ ファイルの場所に格納され、ログ ファイルは SQL Server の既定のログ ファイルの場所に格納されます。
    
4. [**OK**] をクリックします。
    
5. [**データベースの作成**] ページで、[**次へ**] をクリックします。
    
6. [**データベースの作成の完了**] ページで、[**完了**] をクリックします。
    

