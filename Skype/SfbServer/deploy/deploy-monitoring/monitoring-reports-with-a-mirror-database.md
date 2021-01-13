---
title: Skype for Business Server で監視レポートをミラー データベースに関連付ける
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '概要: 監視レポートを Skype for Business Server で使用されるミラー データベースに関連付ける方法について学習します。'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802167"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Skype for Business Server で監視レポートをミラー データベースに関連付ける 
 
**概要:** 監視レポートを Skype for Business Server で使用されるミラー データベースに関連付ける方法について学習します。
  
## <a name="monitor-reports-with-a-mirror-database"></a>ミラー データベースを使用してレポートを監視する

監視データベースのミラーを構成すると、フェールオーバーが発生した場合、そのミラー データベースがプライマリ データベースとして引き継がれします。 ただし、Skype for Business Server 監視レポートを使用してフェールオーバーが発生した場合は、監視レポートがミラー データベースに接続していない可能性があります。 これは、監視レポートをインストールするときに、プライマリ データベースの場所のみを指定するためです。ミラー データベースの場所を指定しない。
  
監視レポートをミラー データベースに自動的にフェールオーバーするには、監視レポートで使用される 2 つのデータベース (通話詳細記録データ用のデータベースと QoE (Quality of Experience) データ用のデータベース) にミラー データベースを "フェールオーバー パートナー" として追加する必要があります。 (この手順は、監視レポートのインストール後に実行する必要があります)。フェールオーバー パートナー情報を追加するには、これら 2 つのデータベースで使用される接続文字列の値を手動で編集します。 これを行うには、次の手順を実行します。
  
1. このInternet Explorer使用して、Reporting **Services SQL Serverページを** 開きます。 Reporting Services ホーム ページの URL には、次が含まれます。
    
   - **http: プレフィックス**。
    
   - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (例: **atl-sql-001.litwareinc.com)。**
    
   - The character string **/Reports_**.
    
   - 監視レポートがインストールされているデータベース インスタンスの名前 **(archinst** など)。
    
     たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされ、監視レポートでデータベース インスタンス archinst が使用されている場合、ホーム ページの URL は次のようになります。
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Reporting Services ホーム ページにアクセスしたら **、[ServerReports]** をクリックし、[レポート] **Reports_Content。** そうすると、Skype for Business Server **Reports_Content** レポートのページが表示されます。
    
3. [次 **Reports_Content** ページで **、CDRDB** データ ソースをクリックします。
    
4. **CDRDB ページの**[プロパティ]**タブで、[** 接続文字列] というラベルの付いたテキスト ボックス **を探します**。 現在の接続文字列は次のように表示されます。
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. 接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含める。 たとえば、サーバーの名前が atl-mirror-001 で、ミラー データベースが archinst インスタンス内にある場合は、次の構文を使用してミラー データベースを指定するために追加する必要があります。
    
    Failover Partner=atl-mirror-001\archinst
    
    編集した接続文字列は次のように表示されます。
    
    Data source=(local)\archinst;フェールオーバー パートナー=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 接続文字列を更新した後、[適用] を **クリックします**。
    
7. **CDRDB ページで**、次のリンク **Reports_Content** クリックします。 **[QOSDB データ** ソース] をクリックし、QoE データベースの接続文字列を編集します。 例:
    
    Data source=(local)\archinst;フェールオーバー パートナー=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. **[適用]** をクリックします。
    
## <a name="see-also"></a>関連項目

[Skype for Business Server での監視レポートのインストール](install-monitoring-reports.md)
  
[Skype for Business Server での監視レポートの使用](../../manage/health-and-monitoring/monitoring-reports.md)
