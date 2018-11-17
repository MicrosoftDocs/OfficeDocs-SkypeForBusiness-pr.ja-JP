---
title: PSTN の使用状況のレポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
description: ビジネス管理センターのレポート領域の新しい Skype では、組織内を呼び出し、オーディオ会議のアクティビティを示しています。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、Skype for Business での PSTN 使用状況の詳細レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 使用状況を把握して、組織内での使用状況を確認するのには請求先の詳細を呼び出すように、呼び出しのコストを含むオーディオ会議の PSTN 使用法の詳細を表示することができます。
ms.openlocfilehash: e4af77832cca1cd2a9d9de49aa83f4400c359277
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561648"
---
# <a name="pstn-usage-report"></a>PSTN の使用状況のレポート

ビジネス管理センター**のレポート**領域の新しい Skype は、組織内を呼び出し、オーディオ会議のアクティビティを示しています。 ここでは、レポートを掘り下げて、各ユーザーのアクティビティについてより細かい洞察を得ることができます。 たとえば、 **Skype for Business での PSTN 使用状況の詳細**レポートを使用して、通話の着信/発信に費やした分数とそれらの通話の料金を確認できます。 使用状況を把握して、組織内での使用状況を確認するのには請求先の詳細を呼び出すように、呼び出しのコストを含むオーディオ会議の PSTN 使用法の詳細を表示することができます。
  
利用可能な他のレポートの[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
このレポートとは、ビジネス レポートの場合は、他の Skype によって、活動を組織全体にわたって使用率の呼び出しなどの詳細情報が表示します。 これらの詳細については、調査する計画、およびその他のビジネスの決定、組織と[の通信のクレジット](/microsoftteams/what-are-communications-credits)を設定するために非常に役に立つ
  
> [!NOTE]
> Office 365 管理センターに管理者としてログオンすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Skype for Business の PSTN 使用状況詳細レポートを取得する方法

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

- **Office 365 管理センター**を参照して > **管理センター** > **ビジネス管理センターの Skype** > **レポート** > **PSTN 使用法の詳細**です。
    
    > [!NOTE]
    > Office 365 のサブスクリプションによっては、ここに表示される製品やレポートの一部が表示されないことがあります。 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Skype for Business PSTN 使用状況レポートを解析する

表示されている各列を見ると、ユーザーの Skype for Business PSTN 使用状況を確認できます。
  
レポートは、このように表示されます。
  
![Skype for Business PSTN 使用状況レポート](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![ナンバー 1](../images/sfbcallout1.png)<br/>この表は、ユーザーごとの、すべての PSTN 使用状況の詳細を示しています。また、Skype for Business が割り当てられているすべてのユーザーと、ユーザーの PSTN 使用状況を示しています。表では、列を追加したり、削除したりすることができます。
*    **通話 ID** は通話の識別番号です。Microsoft サービス サポートへの通話で使用される固有の識別子です。
*    [ **ユーザー ID**] は、ユーザーのサインイン名です。
*    **電話番号**は着信通話を受けた Skype for Business の電話番号、または発信通話でダイヤルされた番号です。
*    **ユーザーの場所**は、ユーザーが使用されている国/地域です。
*    **発信者 ID** は着信通話の発信者電話番号 (発信者 ID) であるか、通話の発信元の番号であるか、発信通話に対して通話の発信元となった Skype for Business 番号です。
*    **型の呼び出し**は、呼び出しが送信または受信の PSTN の呼び出しし、呼び出しの呼び出しなどの型は、ユーザーまたはオーディオ会議で配置したかどうかです。 表示される可能性のある通話の種類は次のとおりです。 

     **通話プランの通話の種類** 
     *    **user_in** (着信 PSTN 通話を受信したユーザー) 
     *    **user_out** (発信 PSTN 通話をかけたユーザー) 
     *    **user_out_conf** (2 つ以上の PSTN 参加者を 3 方向の電話会議などに追加したユーザー) 
     *    **user_out_transfer** (PSTN 番号に通話を転送したユーザー) 
     *    **user_out_forwarding** (PSTN 番号に通話を転送したユーザー)

     **電話会議の通話の種類**
     *    **conf_in**(オーディオ会議用ブリッジに対して着信呼) 
     *    **conf_out** (通常は電話会議に PSTN 番号を追加するための電話会議ブリッジからの発信通話)

     **統合コミュニケーション アプリケーション (UCAP)** 
     *    **ucap_in**(PSTN 着信自動アテンダントまたは呼び出しキューなどの統合コミュニケーション アプリケーションを) 
     *    **ucap_out**(PSTN 発信自動アテンダントまたは呼び出しキューなどの統合コミュニケーション アプリケーションから)
     *    **注:** この PSTN 使用状況レポートに表示されません、自動アテンダントまたは呼び出しキューなど、UC アプリケーションからユーザーに転送された呼び出し呼び出しレグは、ピア ツー ピア (P2P) の音声通話します。 「ツール > Skype のビジネスを呼び出して分析」の下のビジネス管理センターの Skype の P2P の呼び出しにアクセスして日付と時刻での呼び出しを関連付けることや、元の (行 ID の呼び出し) CLID のユーザー名または SIP アドレスを指定して検索しますできます。 
*     
     [ **国内/国際**] は、ユーザーの場所に基づいて通話が国内 (国/地域内) または国際 (国/地域外) のどちらと見なされるかを示します。 
*    **ダイヤル先**は、フランス、ドイツ、アメリカ合衆国 (米国) などがダイヤルされるリンク先の国/地域の名前です。 
*    **数値型**は、ユーザーの電話番号は、サービスまたはフリー ダイヤル番号からの電話番号の種類です。  
*    [ **開始時刻 (UTC)**] は、通話が開始または実行された時刻です。 
*    [ **通話時間**] は、通話が接続されていた時間です。  
*    **ConfID** は電話会議の電話会議 ID です。 
*    [ **料金**] は、アカウントに課金される金額または通話の料金です。 
*    [ **通貨**] は、通話の料金を計算するために使用される通貨の種類です。 
*    [ **機能** ] は通話のために使用されるライセンスです。表示されるライセンスの種類は次のとおりです。 
     *    **MCOPSTNPP** - 通信のクレジット <br/> **MCOPSTN1** - 国内の計画を呼び出す (3000 分米国 1200 分 EU の計画/) 
     *    **MCOPSTN2** - 国際通話プラン 
     *    **MCOPSTN5** - 国内の呼び出しのプラン (120 分の通話プラン) 
     *    **MCOPSTN6** - 国内の呼び出しの計画 (240 分の通話プラン) メモ: 制限された可用性
     *    **MCOMEETADD** - オーディオ会議
     *    **MCOMEETACPEA** - 電話会議の分あたりの支払
> [!NOTE]
> "データはありませんいくつかのフィールドにも表示します。 「データがありません」では、フィールドには適用されない呼び出しの種類や機能を意味します。 
***
![ナンバー 2](../images/sfbcallout2.png)<br/>1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
 ***
![ナンバー 3](../images/sfbcallout3.png)<br/>レポートをエクスポートすることもできます。 タブにデータを区切られて、Excel ファイルをクリックするか、 **Excel にエクスポート**] ボタンをタップします。 <br/><br/> これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype](conference-organizer-activity-report.md)ユーザーが IM、オーディオとビデオ、アプリケーションの共有、Web、アウト ・ サード ・ パーティ、/dial と/dial - を Microsoft を使用して会議を整理する量を確認できます。
    
- [Skype ビジネス会議参加者の設定アクティビティのレポートを](conference-participant-activity-report.md)何 IM、オーディオとビデオ、アプリケーションの共有を参照してください、Web と電話会議ダイヤルアウトが参加しています。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype ビジネス ユーザー向けには、レポートがブロックされています。](users-blocked-report.md)PSTN の呼び出しからブロックされている、組織内のユーザーを表示できます。

- [Skype](pstn-minute-pools-report.md)ビジネス PSTN 分プール レポートの現在の月に、組織内で消費される時間を分単位を表示できます。

- [Skype ビジネス セッション詳細レポート](session-details-report.md)個々 のユーザーの呼び出しの経験についての詳細を表示できます。
    
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
