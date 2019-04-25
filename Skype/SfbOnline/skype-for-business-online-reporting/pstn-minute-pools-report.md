---
title: PSTN の利用分数プール レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: ビジネス管理センターのレポート領域の新しい Skype では、組織内を呼び出し、オーディオ会議のアクティビティを示しています。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 などのビジネス PSTN 分プール レポートの Skype を使用すると、組織内で現在の月の期間中に消費する分の数を参照してください。
ms.openlocfilehash: 903ea97fa5cd187e49db89d0e4db32ad7b851a41
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239900"
---
# <a name="pstn-minute-pools-report"></a>PSTN の利用分数プール レポート

>[!NOTE]
>このレポートには、顧客をプレビューするのにはできるだけです。

ビジネス管理センター**のレポート**領域の新しい Skype は、組織内を呼び出し、オーディオ会議のアクティビティを示しています。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype**ビジネス PSTN 分プールのレポートを使用すると、組織内で現在の月の期間中に消費する分の数を参照してください。
  
利用可能な他のレポートの[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートとは、ビジネス レポートの場合は、他の Skype 詳細を確認できます活動を組織全体にわたって。 これらの詳細については、調査、計画、および組織と[の通信のクレジット](/microsoftteams/what-are-communications-credits)を設定するための他のビジネスの意思決定を行うときに非常に役に立つ
  
> [!NOTE]
> Office 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>ビジネス PSTN 分プール レポートの Skype を取得する方法

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**

- **Office 365 管理センター**を参照して > **管理センター** > **ビジネス管理センターの Skype** > **レポート** > **PSTN の分をプール**します。
    
> [!NOTE]
> によっては、Office 365 サブスクリプションがある場合、可能性があります表示されない場合、同じ詳細を次に示します。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>ビジネス PSTN 分プール レポートの Skype を解釈します。

ビジネス分プールのユーザーの Skype にビューを取得するには、各列に表示されるを見てします。
  
レポートは、このように表示されます。
  
## 

![ビジネス PSTN の分の Skype のプール レポート](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>(機能) のライセンスと使用法の場所での分のプールの内訳を表に示します。 
*    **機能**は、呼び出しに使用されるライセンスおよびサービス プランです。 このレポートに表示されるライセンスおよびサービスの計画は次のとおりです。
     * MCOPSTN1 - 国内の呼び出し (3000 分分 1200 米国と EU の計画の計画
     * MCOPSTN2 - 国内の & 国際を呼び出すことを計画、国内のプール (3000 分 PR/米国/カナダ、1200 分のヨーロッパの国々) と国際プール (600 分) に表示されます。 カレンダー月で国内 OR 国際 cap に達するたびに分の上限に達しました。 
     * MCOPSTN5 - 国内の呼び出しのプラン (120 分の通話プラン)
     * MCOPSTN6 - 国内の呼び出しの計画 (240 分の通話プラン)
     * MCOMEETADD - オーディオ会議
*    **機能の説明**は、呼び出しに使用するライセンスの種類の説明です。
*    **国分のプール**とは、分のプールを共有しているユーザーのライセンス使用状況の場所です。 
*    **使用分**は、1 か月の使用分の数です。
*    **総分数**は、月の利用分の合計数です。 
*    **使用率**は、月の利用時間の割合です。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 <br/><br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 2000 未満のユーザーをした場合は、並べ替えし、フィルター処理、レポート内のテーブル内でします。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype](conference-organizer-activity-report.md)ユーザーが IM、オーディオとビデオ、アプリケーションの共有、Web、アウト ・ サード ・ パーティ、/dial と/dial - を Microsoft を使用して会議を整理する量を確認できます。
    
- [Skype ビジネス会議参加者の設定アクティビティのレポートを](conference-participant-activity-report.md)何 IM、オーディオとビデオ、アプリケーションの共有を参照してください、Web と電話会議ダイヤルアウトが参加しています。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype ビジネス ユーザー向けには、レポートがブロックされています。](users-blocked-report.md)PSTN の呼び出しからブロックされている、組織内のユーザーを表示できます。

- [Skype ビジネス セッション詳細レポート](session-details-report.md)個々 のユーザーの呼び出しの経験についての詳細を表示できます。
    
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
