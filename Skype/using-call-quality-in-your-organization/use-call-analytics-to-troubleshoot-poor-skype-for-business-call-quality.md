---
title: "通話分析を使用して Skype for Business の低い通話品質をトラブルシューティングする"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 6/22/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
description: "Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings."
---

# 通話分析を使用して Skype for Business の低い通話品質をトラブルシューティングする

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](66945036-ae87-4c08-a0bb-984e50d6b009.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/66945036-ae87-4c08-a0bb-984e50d6b009)をクリックしてください。 
  
通話分析により、Skype for Business で発生した通話または接続に関する問題をトラブルシューティングすることができます。通話分析では、お使いの Skype for Business アカウント内の各ユーザーの通話と会議でのデバイス、ネットワーク、接続性についての詳細な情報が示されます。建物。サイト、テナント情報が通話分析に追加されている場合は、それらも各通話およびセッションについて表示されます。通話分析で利用可能な情報により、ユーザーが低品質の通話や会議を経験したことの原因を突き止めることができるようになります。
  
> [!NOTE]
> 通話分析は現在プレビューとして提供されています。ここに記載されるテキストと画像は実際の使用時のものと一致しない可能性があります。 
  
## 通話分析を使用して通話品質の問題をトラブルシューティングする

割り当てられたアクセス許可のレベルによって、通話分析でどの種類の情報にアクセスできるかが決まります。
  
- **Skype for Business 管理者**: 通話分析および Skype for Business 管理センター内のすべての情報にアクセスできます。
    
- **階層 1 のアクセス許可を持つヘルプデスク エージェント**: 通話分析での限られたデータのセットを参照できます。通話のトラブルシューティングを行えますが、会議の問題については階層 2 のエージェントに引き渡すことになります。Skype for Business 管理センターの他の部分にアクセスすることはできません。
    
- **階層 2 のアクセス許可を持つヘルプデスク エージェント**: 通話分析での利用できるデータのすべてを参照できるとともに、通話と会議の両方の問題をトラブルシューティングできます。Skype for Business 管理センターの他の部分にアクセスすることはできません。
    
アクセス許可についてサポートが必要な場合は、お客様の Skype for Business 管理者に相談してください。
  
 **階層 1 または階層 2 のヘルプデスク エージェントとして通話分析を開始する**
  
1. [https://adminportal.services.skypeforbusiness.com](https://adminportal.services.skypeforbusiness.com) に移動して、自分のユーザー名とパスワードを使用してサインインします。
    
2. [ **ユーザー検索**] で、通話のトラブルシューティングを行いたいユーザーの名前または SIP アドレスを入力して、リストからユーザーを選択します。
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. [ **通話履歴**] で、トラブルシューティングしたい通話または会議を選択します。
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. [ **詳細情報**] タブを選択して、低品質や接続の問題を表している黄色および赤色の項目を探します。
    
    各通話または会議のセッションの詳細では、重要でない問題は黄色で表示されます。(たとえば、次のスクリーンショットでは、平均ジッター、最大ジッター、平均パケット損失率の値は黄色で示されています。) 黄色で示されている項目がある場合は、それは標準の範囲から外れていて、問題の要因を成している可能性があるものの、問題の主要な原因ではないだろうと考えられます。赤色で示されている項目がある場合は、それは重大な問題で、このセッションでの低品質の通話の主要な原因である可能性が高いものと考えられます。
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
不具合エクスペリエンスのデータの品質いない音声セッションで受信します。多くの場合これが原因通話ドロップして接続を終了してクライアントを使ってです。 この場合、セッションの評価は""します。
  
Experience (QoE) データの品質が音声セッションでは、次の表は「低下。」としてセッションの対象の点を示します。
  
|**問題**|**エリア**|**説明**|
|:-----|:-----|:-----|
|通話のセットアップ  <br/> |セッション  <br/> |エラー コード Ms 20 ~ 29 を診断では、通話のセットアップに失敗しました。 が表示されます。ユーザーは、通話または会議に参加できませんでした。  <br/> |
|オーディオ ネットワークが低下通話を分類します。  <br/> |セッション  <br/> |ネットワークの品質に問題は、パケット損失、ジッター NMOS 低下、RTT などの領域にあったまたは比率を非表示します。不適切な呼び出しを分類するための条件の詳細については、この[の Microsoft ブログの投稿](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。  <br/> |
|デバイスが機能しません。  <br/> |デバイス  <br/> | デバイスが正しく機能していません。比率が機能していないデバイスは次のとおりです。 <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  
## 関連項目
<a name="MT_Footer"> </a>

#### 

[Skype for Business の通話分析のセットアップ](set-up-skype-for-business-call-analytics.md)

