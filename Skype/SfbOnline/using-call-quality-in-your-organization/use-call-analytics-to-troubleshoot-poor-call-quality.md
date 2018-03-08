---
title: "不適切な Skype for Business のトラブルシューティングに使用する通話分析通話品質"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "Skype for Business 通話と会議のユーザーの問題のトラブルシューティングを行うには、デバイス、ネットワーク、および接続について詳しくは通話の分析を使用します。"
ms.openlocfilehash: 4f43c517beba318889e12fca8b09a488f6da5916
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a>不適切な Skype for Business のトラブルシューティングに使用する通話分析通話品質

通話の分析を使用すると、Skype for Business で通話] または [接続の問題のトラブルシューティングを行うことができます。通話の分析は、Skype for Business アカウントにデバイス、ネットワーク、および通話と会議の各ユーザーの接続に関する詳細情報を示しています。サイト、およびテナントの構築する場合は、情報が追加されている分析の通話を着信およびセッションごとにも表示されます。情報の分析を通話に使用できますが低下通話を持っていた理由を把握する、または会議のエクスペリエンスします。 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>通話の分析を使用して通話品質の問題のトラブルシューティングを行う

情報の種類はどのようなアクセス権のある分析の電話で自分に割り当てられているアクセス許可レベルを決定します。
  
- **Skype for Business 管理者**: 分析を呼び出すと Skype for Business 管理センターですべての情報にアクセス権があります。
    
- **第 1 層のアクセス許可を持つヘルプデスク エージェント**: 通話分析でデータのセットを参照してください。呼び出しのトラブルシューティングを行うことができますが、第 2 の担当者に会議の問題が渡すされます。Business 管理センターの残りの Skype へのアクセスを必要はありません。
    
- **第 2 のアクセス許可を持つヘルプデスク エージェント**: を呼び出す分析のすべての利用可能なデータを表示し、通話と会議の両方の問題のトラブルシューティングを行うことができます。Business 管理センターの残りの Skype へのアクセスを必要はありません。
    
アクセス許可を持つヘルプが必要な場合は、Skype for Business の管理者を参照してください。
  
 **階層 1 または 2 層ヘルプデスク エージェントとして通話の分析を開く**
  
1. Office 365 管理センターに移動し、職場または学校のアカウントを使用してサインインします。[Web ブラウザーで*https://adminportal.services.skypeforbusiness.com*に移動します。
    
2. **ユーザーの検索**] でのトラブルシューティングを行うし、リストからユーザーを選択する呼び出しをユーザーの名前または sip アドレスを入力を開始します。
    
    ![Skype for Business 管理センターでの分析の通話の [ユーザーの検索] ボックスのスクリーン ショット。](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. **通話履歴**には、[トラブルシューティングを行う通話または会議を選択します。
    
    ![スクリーン ショットは、7 日間の品質との会議と電話、アクティビティの概要と、日付と時刻、受信者、および音声の品質の概要については、ユーザーの連絡先の詳細についてなどの情報を持つユーザーの通話履歴] ページを示しています。](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. [**詳細設定**] タブを選択し、低下通話の品質や接続の問題を示す黄色、赤のアイテムを調べます。
    
    各通話または会議のセッションの詳細] では、黄色の小さな問題が表示されます。(たとえば、次のスクリーン ショットでは、値は、黄色の平均ジッター、Max ジッター、平均パケット損失の割合で。)黄色がある場合は、通常の範囲外と、問題が発生する原因なっている可能性がありますがない問題の主な原因をする可能性があります。赤いがある場合は、重要な問題があるし、このセッションの低下通話品質の主な原因である可能性がします。 
    
    ![スクリーン ショットは、つまりマイナーと受信ネットワーク] セクションを展開して、黄色の色] で、平均ジッター、最大ジッター、および平均パケット損失率のデータが表示されているユーザーの通話履歴の詳細設定] タブを示します。](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
不具合エクスペリエンスのデータの品質いない音声セッションで受信します。多くの場合これが原因通話ドロップして接続を終了してクライアントを使ってです。この場合、セッションの評価は""します。
  
Experience (QoE) データの品質が音声セッションでは、次の表は「低下。」としてセッションの対象の点を示します。
  
|**問題**|**領域**|**{Description}**|
|:-----|:-----|:-----|
|通話のセットアップ  <br/> |セッション  <br/> |エラー コード Ms 20 ~ 29 を診断では、通話のセットアップに失敗しました。 が表示されます。ユーザーは、通話または会議に参加できませんでした。  <br/> |
|オーディオ ネットワークが低下通話を分類します。  <br/> |セッション  <br/> |ネットワークの品質に問題は、パケット損失、ジッター NMOS 低下、RTT などの領域にあったまたは比率を非表示します。不適切な呼び出しを分類するための条件の詳細については、この[Microsoft ブログの投稿](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。<br/> |
|デバイスが機能しません。  <br/> |デバイス  <br/> | デバイスが正しく機能していません。比率が機能していないデバイスは次のとおりです。 <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## <a name="related-topics"></a>関連トピック
[Skype for Business 通話分析を設定します。](set-up-call-analytics.md)

[通話の分析手法と通話品質のダッシュ ボードの違いは何ですか。](difference-between-call-analytics-and-call-quality-dashboard.md)

