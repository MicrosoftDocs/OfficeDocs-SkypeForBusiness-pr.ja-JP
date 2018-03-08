---
title: "PSTN の使用状況レポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
description: "新しい Skype for Business 管理センターのレポート] 領域では、組織でする通話、音声会議アクティビティを示しています。各ユーザーのアクティビティに関するより詳細な情報を提供するレポートの詳細を表示することができます。たとえば、Skype for Business PSTN 使用の詳細レポートを使用して、分数で受信/送信の通話時間し、これらの呼び出しのコストを表示することができます。使用状況を把握して、通話、組織内の使用状況を確認する請求明細できるように、通話のコストを含む音声会議 PSTN 使用方法の詳細を表示することができます。"
ms.openlocfilehash: af7e33bc2cdc69d244eed1574ef5a075884f550d
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="pstn-usage-report"></a>PSTN の使用状況レポート

新しい Skype for Business 管理センターの**レポート**] 領域では、組織でする通話、音声会議アクティビティを示しています。各ユーザーのアクティビティに関するより詳細な情報を提供するレポートの詳細を表示することができます。たとえば、 **Skype for Business PSTN の使用方法の詳細**レポートを使用して、分数で受信/送信の通話時間し、これらの呼び出しのコストを表示することができます。使用状況を把握して、通話、組織内の使用状況を確認する請求明細できるように、通話のコストを含む音声会議 PSTN 使用方法の詳細を表示することができます。
  
利用できるその他のレポートの[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートは、その他の Skype for Business レポートと共にによって、組織内の使用の呼び出しを含むアクティビティの詳細情報が表示します。これらの詳細は、調査する計画、およびその他のビジネス決定の組織と[通信クレジット](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)の設定時に非常に便利
  
> [!NOTE]
> すべての Skype for Business のレポートは、Office 365 管理センターに管理者としてログオンするときに表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Skype for Business PSTN 使用の詳細レポートにアクセスする方法

- **Office 365 管理センター**に移動 > **管理センター** > **Skype for Business 管理センター** > **レポート** > **PSTN の使用方法の詳細**。
    
    > [!NOTE]
    > サブスクリプションに応じて、Office 365 がある場合があります表示されない場合、すべての製品とレポートは、次のとおりに表示されます。 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Skype for Business PSTN の使用状況レポートの内容を理解します。

Business PSTN を使用するため、ユーザーの Skype にビューを取得するには、それぞれの表示されている列を確認します。
  
これは、レポートがどのように見えるかです。
  
![Skype for Business PSTN の使用状況レポート](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![数値 1](../images/sfbcallout1.png)<br/>テーブルでは、ユーザーごとのすべての PSTN 使用に関する詳細を表示します。Skype for Business と、PSTN の使い方に割り当てられているすべてのユーザーが表示されます。ことができます列の追加/削除テーブルにします。
*    **Call ID**は、電話の通話 ID です。Microsoft サポートのサービスを呼び出す場合に使用される、通話の一意の識別子することをお勧めします。
*    **ユーザー ID**とは、ユーザーのサインイン名です。
*    **電話番号**は、着信通話を受信した勤務先電話番号または番号発信ダイヤル Skype です。
*    **ユーザーの所在地**は、ユーザーが含まれている国/地域です。
*    **発信者番号**は、着信番号で発信者の電話番号 (発信者) を通話の発信、または会社の番号に通話が発信元の Skype します。
*    **通話の種類**は、通話が発信または受信する PSTN 通話し、など、電話の通話の種類は、ユーザーまたはオーディオ電話会議を配置したかどうか。通話の型が表示されます。 

     **通話プランの呼び出しの種類** 
     *    **user_in**(ユーザーは PSTN 着信を受信) 
     *    **user_out**(ユーザーには、PSTN 発信が配置されている) 
     *    **user_out_conf**(ユーザーは、電話会議 3 方法など、通話に 2 つ以上の PSTN 参加者を追加) 
     *    **user_out_transfer**(ユーザーは PSTN 番号に通話を転送) 
     *    **user_out_forwarding**(ユーザーは PSTN 番号に通話を転送)

     **会議の音声通話の種類**
     *    **conf_in**(電話会議ブリッジに着信通話) 
     *    **conf_out**(発信の音声会議ブリッジから会議に PSTN 番号を追加するには、通常は)

     **統合コミュニケーション アプリケーション (UCAP)** 
     *    **ucap_in**(自動応答または着信キューなど UC アプリケーションに着信通話) 
     *    **ucap_out**(自動応答または着信キューなど UC アプリケーションから発信通話)
*     
     **国内/国際**は配置された通話がユーザーの場所に基づいて、国内 (内での国/地域) または (国/地域) の外部で国際と見なされますかどうかを説明します。 
*    **ダイヤル宛先**は、フランス、ドイツ、米国 (米国) などにダイヤルするリンク先の国/地域の名前です。 
*    **数値型**は、ユーザーの電話番号は、サービスまたはフリー ダイヤル番号から電話番号の種類です。  
*    **開始時刻 (UTC)**は、通話の開始または配置された時間です。 
*    **期間**は、どのくらいの期間、通話が接続されています。  
*    **ConfID**は、音声会議の会議 ID です。 
*    **料金**の金額、自分のアカウントに請求される呼び出しのコスト。 
*    **通貨**は、通話のコストを計算するための通貨の種類です。 
*    **機能**は、通話に使用するライセンスです。ライセンスの型が表示されます。 
     *    **MCOPSTNPP**の通信を加算したもの <br/> **MCOPSTN1** - 国内通話プラン (3000 min 米国 1200 min EU プラン/) 
     *    **MCOPSTN2** - 国際通話プラン 
     *    **MCOPSTN5** - 国内通話プラン (120 分通話プラン) 
     *    **MCOMEETADD** - 電話会議
     *    **MCOMEETACPEA** - 電話会議を分単位の支払 
***
![数値 2](../images/sfbcallout2.png)<br/>すべての 1 つまたは複数の列のデータのグループ化するビューを作成する場合は、**特定の列をグループ化をドラッグ アンド ドロップ**したり、列見出しをここで列をドラッグする] をクリックします。
 ***
![数値 3](../images/sfbcallout3.png)<br/>クリックするか、[ **Excel にエクスポート**] ボタンをタップして、Excel の .csv ファイルにレポートのデータをエクスポートすることもできます。 <br/><br/> これは、すべてのユーザーのデータをエクスポートし、単純な並べ替えとフィルタ リングをさらに詳しく分析を行うことができます。小さい 2000 のユーザーを使っている場合は、並べ替えし、フィルター自体レポートのテーブル内でします。フィルターと並べ替えのために、2000 を超えるユーザーをした場合は、データをエクスポートする必要があります。
   
## <a name="want-to-see-other-skype-for-business-reports"></a>その他の Skype のビジネス レポートを表示したいですか。

- [ビジネス アクティビティ レポートの Skype](activity-report.md)ピア ツー ピア、整理、および会議セッションに参加したユーザーを使用している量を表示できます。
    
- [Skype for Business デバイスの使用状況レポート](device-usage-report.md)Windows ベースのオペレーティング システムを含むデバイスを表示することができ、モバイル デバイスに skype for Business アプリをインストールを使用している IM および会議のします。
    
- [Skype for Business 会議の開催者の活動レポート](conference-organizer-activity-report.md)ユーザーが共有、Web、- サード パーティを/dial と出力 -/dial Microsoft IM、音声/ビデオ、アプリケーションを使用する会議を整理する量を表示できます。
    
- [Skype for Business 会議の参加者の活動レポート](conference-participant-activity-report.md)数 IM、音声/ビデオ、アプリケーションの共有を表示できるは中に参加して Web および音声会議のダイヤルアウトします。
    
- [ピア ツー ピア アクティビティ レポートをビジネスの Skype](peer-to-peer-activity-report.md)ユーザーに IM、音声/ビデオ、アプリケーションの共有とファイルの転送を使用している量を表示できます。
    
- [Skype for Business ユーザーには、レポートがブロックされています。](users-blocked-report.md)PSTN 通話からブロックされている、組織のユーザーを表示できます。

- [Skype for Business PSTN 分プール レポート](pstn-minute-pools-report.md)は、組織内の現在の月の中に使用される時間を分単位で表示できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md)個々 のユーザーの通話エクスペリエンスの詳細を表示できます。
    
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターでのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  

