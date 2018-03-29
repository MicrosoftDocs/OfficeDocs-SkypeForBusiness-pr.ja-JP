---
title: ビジネス サーバー 2015 の Skype でミラー データベースの監視レポートを関連付ける
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '概要: ビジネス サーバー 2015 の Skype で使用されるミラー データベースの監視レポートを関連付ける方法を説明します。'
ms.openlocfilehash: 246f16fd54133e2a6cf1e26a8126d0ec546bd686
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype でミラー データベースの監視レポートを関連付ける
 
**の概要:**監視レポートをビジネス サーバー 2015 Skype で使用するミラー データベースに関連付ける方法について説明します。
  
## <a name="monitor-reports-with-a-mirror-database"></a>ミラー データベースを使用する監視レポート

監視データベースのミラーを構成してあると、フェイルオーバーが発生した場合にそのミラー データベースがプライマリ データベースを引き継ぎます。 ただし、Skype を使用して、サーバーの監視レポートのビジネス、フェールオーバーが発生した場合は、場合があります、監視レポートがミラー データベースに接続していません。 これは、監視レポートをインストールするときにプライマリ データベースの場所だけを指定し、ミラー データベースの場所を指定していないためです。
  
監視レポートがミラー データベースに自動的にフェイルオーバーされるようにするには、監視レポートが使う 2 つのデータベース (通話詳細記録データ用のデータベースと Quality of Experience (QoE) データ用のデータベース) に、ミラー データベースを "フェイルオーバー パートナー" として追加する必要があります (この手順は、監視レポートをインストールした後で実行する必要があります)。フェイルオーバー パートナー情報は、2 つのデータベースが使用する接続文字列の値を手動で編集することで追加できます。この操作を行うには、次の手順に従います。
  
1. Internet Explorer を使って **SQL Server Reporting Services** のホーム ページを開きます。Reporting Services のホーム ページの URL には、次の内容が含まれます。
    
   - プレフィックス **http:**。
    
   - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (**atl-sql-001.litwareinc.com** など)。
    
   - 文字列 **/Reports_**。
    
   - 監視レポートがインストールされているデータベース インスタンスの名前 (**archinst** など)。
    
    たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされており、監視レポートでデータベース インスタンス archinst が使われている場合、ホーム ページの URL は次のようになります。
    
    **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Reporting Services ホーム ページにアクセスしたら、[**ServerReports**]、[**Reports_Content**] の順にクリックします。 クリックすると、 **Reports_Content**ページ、Skype のビジネス サーバー レポートの監視します。
    
3. [**Reports_Content**] ページで、[**CDRDB**] データ ソースをクリックします。
    
4. [**CDRDB**] ページの [**プロパティ**] タブで、[**接続文字列**] というテキスト ボックスを探します。現在の接続文字列は、次のとおりです。
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. 接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含めます。たとえば、サーバーの名前が atl-mirror-001 でミラー データベースが archinst インスタンスにある場合、次の構文を使ってミラー データベースを追加および指定する必要があります。
    
    Failover Partner=atl-mirror-001\archinst
    
    編集された接続文字列は、次のようになります。
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 接続文字列を更新したら、[**適用**] をクリックします。
    
7. [**CDRDB**] ページで、[**Reports_Content**] をクリックします。[**QMSDB**] データ ソースをクリックして、QoE データベースの接続文字列を編集します。次に例を示します。
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. [**適用**] をクリックします。
    
## <a name="see-also"></a>関連項目

#### 

[ビジネス サーバー 2015 の Skype でのレポートの監視をインストールします。](install-monitoring-reports.md)
  
[ビジネス サーバー 2015 の Skype でのレポートの監視を使用します。](../../manage/health-and-monitoring/monitoring-reports.md)

