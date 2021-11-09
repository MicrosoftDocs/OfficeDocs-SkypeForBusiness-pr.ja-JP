---
title: フロントエンド監視ストアの追加ページ
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: '[監視 SQL Server ストアの定義] を行うには、次のプロパティを構成します。'
ms.openlocfilehash: f78105d327b496334de29414b1fa177a4a6380f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839289"
---
# <a name="add-front-end-monitoring-store-page"></a>フロント エンド監視ストア ページの追加
 
[**監視 SQL Server ストアの定義**] を行うには、次のプロパティを構成します。
  
- **監視SQL Server:** リストからSQL Server完全修飾ドメイン名 (および必要に応じてインスタンス) を選択します。
    
    [**新規]** をクリックして、FQDN 定義SQL Server作成し、必要に応じて Monitoring Server ストアのインスタンス名を作成します。
    
- 監視サーバー **にデータベース ミラーリングSQL Server追加** する場合は、[ミラーストアのミラーリングを有効にする] チェック ボックスをオンにします。
    
    リストから既存の **監視 SQL Server ストア ミラー** を選択します。
    
    [**新規]** をクリックして、FQDN 定義SQL Server作成し、必要に応じてミラー ストアのインスタンス名を作成します。
    
- [SQL Server ストア ミラーリング **を有効** にする] を選択した場合は、必要に応じて **[SQL Server** ミラーリング監視を使用する] を選択して自動フェールオーバーを有効にして、一覧から SQL Server ミラーリング監視ストアを選択します。
    
    [**新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を作成します。
    
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。
  
すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[監視ストアをサーバー内のフロントエンド プールに関連付Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
