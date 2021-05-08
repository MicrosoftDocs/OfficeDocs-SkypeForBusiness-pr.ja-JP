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
description: 新しい [管理Skype for Business レポート] 領域には、組織内の通話と電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、PSTN 分Skype for Businessレポートを使用して、組織内の当月に消費された分数を確認できます。
ms.openlocfilehash: d82f360c48b6e7478ef552826ee80ecaf508db0f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238181"
---
# <a name="pstn-minute-pools-report"></a>PSTN の利用分数プール レポート

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>このレポートは、プレビューのお客様にのみ使用できます。

新しい [管理Skype for Business レポート]**領域** には、組織内での通話と電話会議のアクティビティが表示されます。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、PSTN ミニSkype for Businessレポートを使用して、組織内の当月に消費された分数を確認できます。
  
利用可能なその [他のレポートについては](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 、「レポートの概要」を参照してください。
  
このレポートは、他のレポートとSkype for Business、組織全体のアクティビティに関する詳細を示します。 これらの詳細は、組織のその他のビジネス上の決定を調査、計画、および行う場合や、コミュニケーション クレジットを設定する場合に [非常に役立ちます。](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> 管理者として管理センターにログオンSkype for Business、すべてのレポートをMicrosoft 365できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>PSTN ミニSkype for Business レポートにアクセスする方法

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センターに移動し、[管理センター>**管理センター Skype for Business** PSTN 分プールを  >    >    >  **報告します**。
    
> [!NOTE]
> サブスクリプションのMicrosoft 365またはOffice 365によっては、ここに示す同じ詳細が表示されない場合があります。 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>PSTN 分Skype for Businessレポートを解釈する

表示される各列を確認することで、Skype for Business分のプールを表示できます。
  
レポートは、このように表示されます。
  
## 

![Skype for BusinessPSTN 分プール レポート](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/>次の表は、ライセンス (機能) と使用場所別の分プールの内訳を示しています。 
*    **機能** は、呼び出しに使用されるライセンス/サービス プランです。 このレポートに表示されるライセンス/サービス プランは次のとおりです。
     * MCOPSTN1 - 国内通話プラン (3000 分米国/1200 分の EU プラン)
     * MCOPSTN2 - 国内プール (3000 分米国/カナダ/PR、ヨーロッパ 1200 分の国) と国際プール (600 分) が表示される国内 & 国際通話プラン。 分の上限は、カレンダー月内に国内の -OR - 国際上限に達するたびに達します。 
     * MCOPSTN5 - 国内通話プラン (120 分の通話プラン)
     * MCOPSTN6 - 国内通話プラン (240 分の通話プラン)
     * MCOMEETADD - 電話会議
*    **機能の** 説明は、呼び出しに使用されるライセンスの種類の説明です。
*    **国の分のプール** は、分のプールを共有するユーザーのライセンス使用場所です。 
*    **[分数]** は、毎月使用される分数です。
*    **[分の** 合計] は、その月に使用できる合計分数です。 
*    **[使用した** 割合] は、その月に使用される分数の割合です。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。 
***
![ナンバー 3](../images/sfbcallout3.png)<br/>また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 <br/><br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2,000 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行います。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business開催者アクティビティ レポートの作成](conference-organizer-activity-report.md)IM、音声/ビデオ、アプリケーション共有、Web、/dial out - サードパーティ、/ダイヤルアウト - Microsoft を使用する会議をユーザーがどれだけ開催しているか確認できます。
    
- [Skype for Business参加者アクティビティ レポートの作成](conference-participant-activity-report.md)参加している IM、音声/ビデオ、アプリケーション共有、Web およびダイヤルアウト音声会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Businessブロックレポート](users-blocked-report.md)PSTN 通話がブロックされている組織内のユーザーを確認できます。

- [Skype for Business詳細レポート](session-details-report.md)個々のユーザーの通話エクスペリエンスに関する詳細を確認できます。
    
## <a name="related-topics"></a>関連トピック
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
