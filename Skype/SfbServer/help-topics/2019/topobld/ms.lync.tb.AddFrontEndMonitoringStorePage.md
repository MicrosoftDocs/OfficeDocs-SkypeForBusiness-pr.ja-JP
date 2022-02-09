---
title: フロントエンド監視ストアの追加ページ
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 9ba6a6d6481f36eb7a7a28ec91881b60429b3fcd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398150"
---
# <a name="add-front-end-monitoring-store-page"></a>フロント エンド監視ストア ページの追加
 
[**監視 SQL Server ストアの定義**] を行うには、次のプロパティを構成します。
  
- **監視SQL Server:** リストからSQL Server完全修飾ドメイン名 (および必要に応じてインスタンス) を選択します。
    
    [**新規]** をクリックして、FQDN 定義SQL Server作成し、必要に応じて監視サーバー ストアのインスタンス名を作成します。
    
- 監視サーバー **にデータベース ミラーリングSQL Server** する場合は、[ストア ミラーリングを有効にする] チェック ボックスをオンにします。
    
    リストから既存の **監視 SQL Server ストア ミラー** を選択します。
    
    [**新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラー ストアのインスタンス名を作成します。
    
- [SQL Server ストア ミラーリング **を** 有効にする] を選択した場合は、必要に応じて [**SQL Server** ミラーリング監視を使用する] を選択して自動フェールオーバーを有効にして、一覧から SQL Server ミラーリング監視ストアを選択します。
    
    [**新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を作成します。
    
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。
  
すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[監視ストアをサーバー内のフロントエンド プールに関連付Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
