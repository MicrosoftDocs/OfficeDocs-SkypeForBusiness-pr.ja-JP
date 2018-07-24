---
title: データベースの作成
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーは、SQL Server にデータベースをインストールする方法を提供します。 トポロジ ビルダーを使用してデータベースをインストールしてアプリケーション トポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースがインストールされます。 トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。 特定のコンピューター上の特定のデータベースをインストールする必要がありますか、Windows PowerShell のコマンド ライン インターフェイスおよびインストール CsDatabase コマンドレットが代わりに使用する必要がある場合は配置されているデータベースをインストールする必要があります。
ms.openlocfilehash: 087bed64e0e1d53cd610433c5695899107a9aa71
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21066113"
---
# <a name="create-database"></a>データベースの作成
 
トポロジ ビルダーは、SQL Server にデータベースをインストールする方法を提供します。 トポロジ ビルダーを使用してデータベースをインストールしてアプリケーション トポロジから情報を読み取り、指定された SQL Server コンピューターまたは SQL Server クラスターに必要なデータベースがインストールされます。 トポロジ ビルダーを使用したデータベースのインストールは、この方法のみです。 特定のコンピューター上の特定のデータベースをインストールする必要がありますか、Windows PowerShell のコマンド ライン インターフェイスおよび[インストール CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps)コマンドレットが代わりに使用する必要がある場合は配置されているデータベースをインストールする必要があります。
  
### <a name="creating-a-database"></a>データベースの作成

1. ビジネス サーバー ノードの Skype をクリックし、**データベースのインストール**] をクリックします。
    
2. [**データベースの作成**] ページで、**データベースのインストール**] ダイアログ ボックスで新しいデータベースが作成される SQL Server ストアの完全修飾ドメイン名 (FQDN) を選択します。
    
3. [**詳細設定**] をクリックします。[**データベース ファイルの場所の選択**] ダイアログ ボックスで、次のどちらかのオプションを選択します。
    
  - [**データベース ファイルの場所を自動的に判断する**]。このオプションを選択すると、トポロジ ビルダーは、組み込みのアルゴリズムを使用して、データベースのログ ファイルとデータ ファイルの格納場所を選択します。
    
  - [**既定の SQL Server インスタンスを使用する**]。 このオプションを選択すると、データベースのログ ファイルとデータ ファイルの格納場所を選択するために、組み込みのアルゴリズムは使用されません。 代わりに、ログ ファイルとデータ ファイルは、(これらのパスする必要があります構成で SQL Server の管理者が高度な) SQL Server の既定のパスで指定された場所に格納されます。 データ ファイルは SQL Server の既定のデータ ファイルの場所に格納され、ログ ファイルは SQL Server の既定のログ ファイルの場所に格納されます。
    
4. [**OK**] をクリックします。
    
5. [**データベースの作成**] ページで、[**次へ**] をクリックします。
    
6. [**データベースの作成の完了**] ページで、[**完了**] をクリックします。
    

