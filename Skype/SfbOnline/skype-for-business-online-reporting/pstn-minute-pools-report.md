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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: '[新しい Skype for Business 管理センターのレポート] 領域には、組織内の電話会議アクティビティと電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、Skype for Business PSTN 分プールレポートを使用して、組織内の現在の月に消費された分数を確認することができます。'
ms.openlocfilehash: ac27e88b6e0f4945dde90f5e5f7bade31f20fe6a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776252"
---
# <a name="pstn-minute-pools-report"></a>PSTN の利用分数プール レポート

>[!NOTE]
>このレポートは、プレビュー版のお客様のみご利用いただけます。

[新しい Skype for Business 管理センターの**レポート**] 領域には、組織内の電話会議アクティビティと電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype For BUSINESS PSTN 分プール**レポートを使用して、組織内の現在の月に消費された分数を確認することができます。
  
利用可能なその他のレポートについては、 [「レポートの概要」](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートと他の Skype for Business レポートを使用すると、組織全体のアクティビティについて詳しく知ることができます。 これらの情報は、組織のビジネスに関する調査、計画、その他の意思決定の際に非常に役立ちます。また、[通信クレジット](/microsoftteams/what-are-communications-credits)を設定することも可能です。
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Skype for Business PSTN 分プールレポートを取得する方法

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センターに移動して >**管理** > **センター Skype for business 管理センター** > **レポート** > **PSTN 分のプール**をレポートします。
    
> [!NOTE]
> Microsoft 365 または Office 365 のサブスクリプションによっては、ここに示されているすべての詳細が表示されない場合があります。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Skype for Business PSTN 分のプールレポートを解釈する

表示されている各列を見ると、ユーザーの Skype for Business の分数プールを確認できます。
  
レポートは、このように表示されます。
  
## 

![Skype for Business PSTN 分プールレポート](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![ナンバー 1](../images/sfbcallout1.png)<br/>この表には、ライセンス (機能) と使用状況の場所によって、分単位のプールの内訳が表示されています。 
*    **機能**は、通話に使用されるライセンス/サービスプランです。 このレポートには、次のようなライセンス/サービスプランが表示されます。
     * MCOPSTN1-国内通話プラン (3000-US/1200 分の EU プラン)
     * MCOPSTN2-国内 & 国際通話プラン (3000-米国/カナダ/PR、1200年のヨーロッパ諸国)、および国際プール (600-分) が表示されます。 予定表の月内で国内または国際通話の上限に達したときに、分数の上限に達しました。 
     * MCOPSTN5-国内通話プラン (120 分通話プラン)
     * MCOPSTN6-国内通話プラン (240 分通話プラン)
     * MCOMEETADD-電話会議
*    **機能の説明**は、通話に使用されるライセンスの種類の説明です。
*    [**国の分数プール**] は、分数プールを共有するユーザーのライセンス使用場所です。 
*    [**使用時間 (分)** は、毎月使用される分数 (分) です。
*    "**合計分数**" は、その月で利用可能な分数の合計数です。 
*    [**使用率 (%)** は、月に使用される分数のパーセントです。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 <br/><br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が2000より少ない場合は、レポート内のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype For business 電話会議開催者アクティビティレポート](conference-organizer-activity-report.md)IM、音声/ビデオ、アプリケーション共有、Web、/ダイヤルアウト-サードパーティ、およびダイヤルアウト-Microsoft を使用して、ユーザーが会議をどの程度管理しているかを確認できます。
    
- [Skype For business 電話会議参加者アクティビティレポート](conference-participant-activity-report.md)IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルアウト音声会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype For business ユーザーがブロック](users-blocked-report.md)されたレポートPSTN 通話の発信をブロックされている組織内のユーザーを確認できます。

- [Skype For business セッションの詳細レポート](session-details-report.md)個々のユーザの通話エクスペリエンスについての詳細を見ることができます。
    
## <a name="related-topics"></a>関連トピック
[管理センターでのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
