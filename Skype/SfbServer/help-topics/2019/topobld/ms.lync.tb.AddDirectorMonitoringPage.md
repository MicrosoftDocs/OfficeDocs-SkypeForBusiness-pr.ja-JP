---
title: ディレクターの監視を追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
ROBOTS: NOINDEX, NOFOLLOW
description: 以下のプロパティを構成することにより、監視 SQL Server ストアの定義を行えます。
ms.openlocfilehash: b2e1c0781529e4e7e1d8904561cf2fe3decaab8c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839399"
---
# <a name="add-director-monitoring"></a>ディレクターの監視の追加
 
以下のプロパティを構成することにより、**監視 SQL Server ストアの定義** を行えます。
  
- **監視SQL Server:** リストからSQL Server完全修飾ドメイン名 (FQDN) (および、必要に応じて名前付き SQL Server インスタンス) を選択します。
    
    [**新規]** をクリックして、FQDN 定義SQL Server作成し、必要に応じて監視サーバー ストアのインスタンス名を作成します。
    
- 監視サーバー **にデータベース ミラーリングSQL Server追加** する場合は、[ミラーストアのミラーリングを有効にする] チェック ボックスをオンにします。
    
    リストから既存の **監視 SQL Server ストア ミラー** を選択します。
    
    [**新規]** をクリックして、新SQL Server FQDN 定義を作成し、必要に応じてミラー ストアのインスタンス名を作成します。
    
- [SQL Server ストア ミラーリング **を有効** にする] を選択した場合は、必要に応じて **[SQL Server** ミラーリング監視を使用する] を選択して自動フェールオーバーを有効にして、一覧から SQL Server ミラーリング監視ストアを選択します。
    
    [**新規]** をクリックして、FQDN 定義SQL Server作成し、必要に応じてミラーリング監視ストアのインスタンス名を作成します。
    
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
このダイアログのオプションの入力が完了したら、[**次へ**] をクリックして、構成を続行します。
  
すべての変更を破棄し、ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  

