---
title: ブロックされているユーザーのレポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
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
description: 'このレポートとは、ビジネス レポートの場合は、他の Skype によって、PSTN の使用法を含む、組織全体での活動の詳細情報が表示します。 '
ms.openlocfilehash: 789f881aff2f80603ac440250bc769d6c7b989c0
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532687"
---
# <a name="users-blocked-report"></a>ブロックされているユーザーのレポート

ビジネス**レポート**のダッシュ ボードの新しい Skype によって、組織内のビジネス製品の Skype 経由でアクティビティの概要がわかります。 各製品内のアクティビティに関するより詳細な洞察を提供する個々 の製品レベルのレポートへドリルすることができます。 たとえば、 **Skype**がブロックされているビジネス ユーザーのレポートを使用すると、PSTN の呼び出しからブロックされている、組織内のユーザーを参照してください。 このレポートとは、ビジネス レポートの場合は、他の Skype によって、PSTN の使用法を含む、組織全体での活動の詳細情報が表示します。
  
 利用可能な他のレポートの[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
> [!NOTE]
> 管理者として Office 365 の管理センターにサインインするときに、ビジネス レポートの Skype のすべてを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>ビジネス ユーザー向け Skype を取得する方法は、レポートをブロックします。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**

- **Office 365 管理センター**を参照して > **管理センター** > **ビジネス管理センターの Skype** > **レポート** > **のユーザーがブロックされています**。
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Skype のビジネス ユーザーがブロックされているレポートを解釈します。

禁止されているユーザーにビューを取得するには、各列に表示されます。
  
レポートは、このように表示されます。 
  
![禁止されているユーザーのレポート](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

テーブルでは、呼び出しからブロックされているユーザーのすべての分類を示します。 電話システムまたはそれらに割り当てられた電話会議を持っているすべてのユーザーが表示されます。 表では、列を追加したり、削除したりすることができます。
***
![ナンバー 1](../images/sfbcallout1.png)
*   **ユーザー ID**は、ユーザーのサインインには。
*   **電話番号**は、ユーザーに割り当てられている番号です。 
*   **ブロック操作**は、呼び出しを行うユーザーがブロックされた時刻 (UTC) です。
*   **ブロック操作**は、ユーザーを禁止するのには実行されたアクションの種類です。
*   **ブロック アクションの理由**は、ユーザーは、呼び出しでブロックされています理由です。
***
![ナンバー 2](../images/sfbcallout2.png)<br/>
1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
***
![ナンバー 3](../images/sfbcallout3.png)<br/>
また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 2000 未満のユーザーをした場合は、並べ替えし、フィルター処理、レポート内のテーブル内でします。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype ビジネス会議参加者の設定アクティビティのレポートを](conference-participant-activity-report.md)何 IM、オーディオとビデオ、アプリケーションの共有を参照してください、Web やダイアル ・ イン/アウトの会議の会議が参加しています。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype ビジネス PSTN の使用状況レポート](pstn-usage-report.md)送信/受信の呼び出しに費やされ、これらの呼び出しのコストの数分の数を表示できます。

- [Skype](pstn-minute-pools-report.md)ビジネス PSTN 分プール レポートの現在の月に、組織内で消費される時間を分単位を表示できます。

- [Skype ビジネス セッション詳細レポート](session-details-report.md)個々 のユーザーの呼び出しの経験についての詳細を表示できます。
   
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 