---
title: フロントエンド監視ストアの追加ページ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: '[監視 SQL Server ストアの定義] を行うには、次のプロパティを構成します。'
ms.openlocfilehash: e867ec998e1380e70125d0ad743f83b06737758e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811667"
---
# <a name="add-front-end-monitoring-store-page"></a>フロント エンド監視ストア ページの追加
 
[**監視 SQL Server ストアの定義**] を行うには、次のプロパティを構成します。
  
- **監視SQL Server:** リストSQL Server完全修飾ドメイン名 (およびオプションでインスタンス) を選択します。
    
    [ **新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じて監視サーバー ストアのインスタンス名を作成します。
    
- 監視サーバー **にSQL Serverミラーリング** を追加する場合は、[ストア ミラーリングを有効にする] チェック ボックスをオンにします。
    
    リストから既存の **監視 SQL Server ストア ミラー** を選択します。
    
    [ **新規]** をクリックして、新SQL Server FQDN 定義と、必要に応じてミラー ストアのインスタンス名を作成します。
    
- [SQL Server ストアミラーリングを有効にする] を選択した場合は、必要に応じて **[SQL Server** ミラーリング監視を使用する] を選択して自動フェールオーバーを有効にし、一覧から SQL Server ミラーリング監視ストアを選択します。
    
    [ **新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラーリング監視ストアのインスタンス名を作成します。
    
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。
  
すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server のフロントエンド プールに監視ストアを関連付ける](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
