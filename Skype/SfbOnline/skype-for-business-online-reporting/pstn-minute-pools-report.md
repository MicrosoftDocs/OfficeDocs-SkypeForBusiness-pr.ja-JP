---
title: "PSTN 分プール レポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "新しい Skype for Business 管理センターのレポート] 領域では、組織でする通話、音声会議アクティビティを示しています。各ユーザーのアクティビティに関するより詳細な情報を提供するレポートの詳細を表示することができます。たとえば、Skype for Business PSTN 分プール レポートを使用すると、組織内の現在の月の中に使用される時間を分単位を参照してください。"
ms.openlocfilehash: f0cb22187fe8b791ef143524eeae6b453f89f4f4
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="pstn-minute-pools-report"></a>PSTN 分プール レポート

>[!NOTE]
>このレポートには、顧客をプレビューするのにはできるだけです。

新しい Skype for Business 管理センターの**レポート**] 領域では、組織でする通話、音声会議アクティビティを示しています。各ユーザーのアクティビティに関するより詳細な情報を提供するレポートの詳細を表示することができます。たとえば、 **Skype for Business PSTN 分プール**レポートを使用すると、分数、組織内の現在の月の使用を参照してください。
  
利用できるその他のレポートの[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートと、その他の Skype for Business のレポート、詳細を確認できますアクティビティで、組織全体でします。これらの詳細については、調査、計画、および他のビジネス決定の組織と[通信クレジット](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)の設定を行うときに非常に便利
  
> [!NOTE]
> すべての Skype for Business のレポートは、Office 365 管理センターに管理者としてログオンするときに表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Skype for Business PSTN 分プール レポートにアクセスする方法

- **Office 365 管理センター**に移動 > **管理センター** > **Skype for Business 管理センター** > **レポート** > **PSTN 分プール**します。
    
> [!NOTE]
> によっては、Office 365 サブスクリプションがある場合があります表示されない場合、同じ詳細をここに示します。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Skype for Business PSTN 分プールのレポートの内容を理解します。

Minute プールのビジネス ユーザーの Skype にビューを取得するには、それぞれの表示されている列を確認します。
  
これは、レポートがどのように見えるかです。
  
## 

![Skype for Business PSTN 分プール レポート](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>表には、ライセンス (能力) や利用場所によって分プールの内訳を示します。 
*    **機能**は、通話に使用するライセンス/サービス プランがあります。このレポートに表示されるライセンス/サービス プランは次のとおりです。
     * MCOPSTNPP の通信を加算したもの
     * MCOPSTN1 - 国内通話を計画する (3000 分米国/1200 分 EU プラン
     * MCOPSTN2 - 国際通話プラン
     * MCOPSTN5 - 国内通話プラン (120 分通話プラン)
     * MCOMEETADD - 電話会議
     * MCOMEETACPEA - 電話会議を分単位の支払
*    **機能の説明**は、通話に使用するライセンスの種類の説明です。
*    **国分プール**とは、分の共有元を共有しているユーザーのライセンスの利用場所です。 
*    **分の使用**は、1 か月を使用する分数の数です。
*    **合計分数**は、月の利用可能な分の総数です。 
*    無料通話分の月の使用率は、**率 (%) を使用**します。 
***
![数値 2](../images/sfbcallout2.png)<br/>すべての 1 つまたは複数の列のデータのグループ化するビューを作成する場合は、**特定の列をグループ化をドラッグ アンド ドロップ**したり、列見出しをここで列をドラッグする] をクリックします。 
***
![数値 3](../images/sfbcallout3.png)<br/>クリックするか、[ **Excel にエクスポート**] ボタンをタップして、Excel の .csv ファイルにレポートのデータをエクスポートすることもできます。 <br/><br/> これは、すべてのユーザーのデータをエクスポートし、単純な並べ替えとフィルタ リングをさらに詳しく分析を行うことができます。少ない 2000 のユーザーを使っている場合は、並べ替えし、フィルター自体レポートのテーブル内でします。フィルターと並べ替えのために、2000 を超えるユーザーをした場合は、データをエクスポートする必要があります。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>その他の Skype のビジネス レポートを表示したいですか。

- [ビジネス アクティビティ レポートの Skype](activity-report.md)ピア ツー ピア、整理、および会議セッションに参加したユーザーを使用している量を表示できます。
    
- [Skype for Business デバイスの使用状況レポート](device-usage-report.md)Windows ベースのオペレーティング システムを含むデバイスを表示することができ、モバイル デバイスに skype for Business アプリをインストールを使用している IM および会議のします。
    
- [Skype for Business 会議の開催者の活動レポート](conference-organizer-activity-report.md)ユーザーが共有、Web、- サード パーティを/dial と出力 -/dial Microsoft IM、音声/ビデオ、アプリケーションを使用する会議を整理する量を表示できます。
    
- [Skype for Business 会議の参加者の活動レポート](conference-participant-activity-report.md)数 IM、音声/ビデオ、アプリケーションの共有を表示できるは中に参加して Web および音声会議のダイヤルアウトします。
    
- [ピア ツー ピア アクティビティ レポートをビジネスの Skype](peer-to-peer-activity-report.md)ユーザーに IM、音声/ビデオ、アプリケーションの共有とファイルの転送を使用している量を表示できます。
    
- [Skype for Business ユーザーには、レポートがブロックされています。](users-blocked-report.md)PSTN 通話からブロックされている、組織のユーザーを表示できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md)個々 のユーザーの通話エクスペリエンスの詳細を表示できます。
    
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターでのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  