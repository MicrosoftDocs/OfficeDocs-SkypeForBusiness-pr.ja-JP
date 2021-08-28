---
title: 監視レポートとミラー データベースの関連付けSkype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '概要: 監視レポートを、ユーザーが使用するミラー データベースに関連付けるSkype for Business Server。'
ms.openlocfilehash: 723d01f732259098c714eaac330eeaf8c686acac
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600662"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>監視レポートとミラー データベースの関連付けSkype for Business Server 
 
**概要:** 監視レポートを、ユーザーが使用するミラー データベースに関連付けるSkype for Business Server。
  
## <a name="monitor-reports-with-a-mirror-database"></a>ミラー データベースを使用してレポートを監視する

監視データベースのミラーを構成すると、フェールオーバーが発生した場合、そのミラー データベースがプライマリ データベースとして引き継がれします。 ただし、監視レポートSkype for Business Server使用してフェールオーバーが発生した場合は、監視レポートがミラー データベースに接続していない可能性があります。 これは、監視レポートをインストールするときに、プライマリ データベースの場所のみを指定するためです。ミラー データベースの場所を指定しない。
  
監視レポートをミラー データベースに自動的にフェールオーバーするには、監視レポートで使用される 2 つのデータベース (通話詳細レコード データ用の 1 つのデータベース、および QoE データ用のもう 1 つのデータベース) にミラー データベースを "フェールオーバー パートナー" として追加する必要があります。 (この手順は、監視レポートのインストール後に実行する必要があります。これら 2 つのデータベースで使用される接続文字列の値を手動で編集することで、フェールオーバー パートナー情報を追加できます。 これを行うには、次の手順を実行します。
  
1. [Internet Explorerを使用して、ホーム **ページSQL Server Reporting Services** 開きます。 Reporting Services のホーム ページ URL には、次の情報が含まれます。
    
   - **http:** プレフィックス。
    
   - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (たとえば **、atl-sql-001.litwareinc.com)。**
    
   - 文字列 **/Reports_**。
    
   - 監視レポートがインストールされているデータベース インスタンスの名前 (たとえば **、archinst)。**
    
     たとえば、SQL Server Reporting Servicesがコンピューター atl-sql-001.litwareinc.com にインストールされ、監視レポートでデータベース インスタンス archinst が使用されている場合、ホーム ページの URL は次のようになります。
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Reporting Services のホーム ページにアクセスしたら **、[ServerReports]** をクリックし、[次へ] をクリック **Reports_Content。** この場合、監視 **レポートReports_Contentページ** Skype for Business Server表示されます。
    
3. [データ **Reports_Content]** ページで **、CDRDB データ ソースを** クリックします。
    
4. **CDRDB ページの**[プロパティ]**タブ** で、[接続文字列] というラベルの付いたテキスト ボックス **を探します**。 現在の接続文字列は次のように表示されます。
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. 接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含める。 たとえば、サーバーの名前が atl-mirror-001 で、ミラー データベースが archinst インスタンスにある場合は、次の構文を使用してミラー データベースを指定するために追加する必要があります。
    
    フェールオーバー パートナー=atl-mirror-001\archinst
    
    編集した接続文字列は次のように表示されます。
    
    Data source=(local)\archinst;フェールオーバー パートナー=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 接続文字列を更新した後、[適用] を **クリックします**。
    
7. **[CDRDB] ページ** で、[追加] リンク **Reports_Content** クリックします。 **[QMSDB]** データ ソースをクリックし、QoE データベースの接続文字列を編集します。 次に例を示します。
    
    Data source=(local)\archinst;フェールオーバー パートナー=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. **[適用]** をクリックします。
    
## <a name="see-also"></a>関連項目

[[監視レポートのインストール] Skype for Business Server](install-monitoring-reports.md)
  
[[監視レポートの使用] Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
