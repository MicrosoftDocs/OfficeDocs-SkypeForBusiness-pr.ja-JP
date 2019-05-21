---
title: Skype for Business Server のミラーデータベースに監視レポートを関連付ける
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '概要: Skype for Business Server で使用されているミラーデータベースに監視レポートを関連付ける方法について説明します。'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273967"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Skype for Business Server のミラーデータベースに監視レポートを関連付ける 
 
**概要:** Skype for Business Server で使用されているミラーデータベースで監視レポートを関連付ける方法について説明します。
  
## <a name="monitor-reports-with-a-mirror-database"></a>ミラー データベースを使用する監視レポート

監視データベースのミラーを構成してあると、フェイルオーバーが発生した場合にそのミラー データベースがプライマリ データベースを引き継ぎます。 ただし、Skype for Business Server Monitoring レポートを使用してフェールオーバーが発生した場合は、監視レポートがミラーデータベースに接続されていない可能性があります。 これは、監視レポートをインストールするときにプライマリ データベースの場所だけを指定し、ミラー データベースの場所を指定していないためです。
  
監視レポートがミラー データベースに自動的にフェイルオーバーされるようにするには、監視レポートが使う 2 つのデータベース (通話詳細記録データ用のデータベースと Quality of Experience (QoE) データ用のデータベース) に、ミラー データベースを "フェイルオーバー パートナー" として追加する必要があります (この手順は、監視レポートをインストールした後で実行する必要があります)。フェイルオーバー パートナー情報は、2 つのデータベースが使用する接続文字列の値を手動で編集することで追加できます。この操作を行うには、次の手順に従います。
  
1. Internet Explorer を使って **SQL Server Reporting Services** のホーム ページを開きます。Reporting Services のホーム ページの URL には、次の内容が含まれます。
    
   - プレフィックス **http:**。
    
   - Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (**atl-sql-001.litwareinc.com** など)。
    
   - 文字列 **/Reports_**。
    
   - 監視レポートがインストールされているデータベース インスタンスの名前 (**archinst** など)。
    
     たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされており、監視レポートでデータベース インスタンス archinst が使われている場合、ホーム ページの URL は次のようになります。
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Reporting Services ホーム ページにアクセスしたら、[**ServerReports**]、[**Reports_Content**] の順にクリックします。 これにより、Skype for Business Server Monitoring レポートの**Reports_Content**ページに移動します。
    
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

[Skype for Business Server で監視レポートをインストールする](install-monitoring-reports.md)
  
[Skype for Business Server で監視レポートを使用する](../../manage/health-and-monitoring/monitoring-reports.md)
