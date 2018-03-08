---
title: "ブロックされているユーザー レポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
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
description: "このレポートは、ビジネス レポートの場合、その他の Skype とによってを組織全体で PSTN の使用を含むアクティビティの詳細情報が表示されます。 "
ms.openlocfilehash: 4a3ca5b29a6be75f2f03890d4447b9c62c966c92
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="users-blocked-report"></a>ブロックされているユーザー レポート

新しい Skype for Business の**レポート**のダッシュ ボードによって、Skype for Business 製品を組織内でのアクティビティの概要がわかります。各製品内で活動に関するより詳細な情報を提供する個別の製品レベル レポート ドリルダウンすることができます。たとえば、 **Skype for Business ユーザーがブロックされている**レポートを使用すると、PSTN 通話からブロックされている、組織のユーザーを参照してください。このレポートは、ビジネス レポートの場合、その他の Skype とによってを組織全体で PSTN の使用を含むアクティビティの詳細情報が表示されます。
  
 利用できるその他のレポートの[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
> [!NOTE]
> すべての Skype for Business のレポートは、Office 365 管理センターに管理者としてログオンするときに表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Skype for Business ユーザーにアクセスする方法には、レポートがブロックされています。

- **Office 365 管理センター**に移動 > **管理センター** > **Skype for Business 管理センター** > **レポート** > **ユーザーをブロック**します。
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Skype for Business のユーザーがブロックされているレポートの内容を理解します。

禁止されているユーザーにビューを取得するには、各列に表示されます。
  
これは、レポートがどのように見えるかです。 
  
![ブロックされたユーザー レポート](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

表には、すべての発信がブロックされているユーザーの内訳を示します。ユーザーが電話システムや電話会議が割り当てられているすべてのユーザーが表示されます。ことができます列の追加/削除テーブルにします。
***
![数値 1](../images/sfbcallout1.png)
*   **ユーザー ID**では、ユーザーのサインインします。
*   **電話番号**は、ユーザーに割り当てられている番号です。 
*   **ブロックのアクション**は、ユーザーから発信することがブロックされた時刻 (UTC) です。
*   **ブロックのアクション**は、ユーザーをブロックするのには実行されたアクションの種類です。
*   **ブロック アクション理由**は、ユーザーがから発信することがブロックされている理由です。
***
![数値 2](../images/sfbcallout2.png)<br/>
すべての 1 つまたは複数の列のデータのグループ化するビューを作成する場合は、**特定の列をグループ化をドラッグ アンド ドロップ**したり、列見出しをここで列をドラッグする] をクリックします。
***
![数値 3](../images/sfbcallout3.png)<br/>
クリックするか、[ **Excel にエクスポート**] ボタンをタップして、Excel の .csv ファイルにレポートのデータをエクスポートすることもできます。

これは、すべてのユーザーのデータをエクスポートし、単純な並べ替えとフィルタ リングをさらに詳しく分析を行うことができます。少ない 2000 のユーザーを使っている場合は、並べ替えし、フィルター自体レポートのテーブル内でします。フィルターと並べ替えのために、2000 を超えるユーザーをした場合は、データをエクスポートする必要があります。
***

## <a name="want-to-see-other-skype-for-business-reports"></a>その他の Skype のビジネス レポートを表示したいですか。

- [ビジネス アクティビティ レポートの Skype](activity-report.md)ピア ツー ピア、整理、および会議セッションに参加したユーザーを使用している量を表示できます。
    
- [Skype for Business デバイスの使用状況レポート](device-usage-report.md)Windows ベースのオペレーティング システムを含むデバイスを表示することができ、モバイル デバイスに skype for Business アプリをインストールを使用している IM および会議のします。
    
- [Skype for Business 会議の開催者の活動レポート](conference-organizer-activity-report.md)ユーザーが IM、音声/ビデオ、アプリケーションの共有、Web、ダイヤルアウトの/-サード パーティの場合、およびで/ダイヤルアウト - Microsoft を使用する会議を整理する度合いを表示できます。
    
- [Skype for Business 会議の参加者の活動レポート](conference-participant-activity-report.md)IM、音声/ビデオ、アプリケーションの共有、Web の数を表示し、/ダイヤルアウトで会議の会議が参加するとします。
    
- [ピア ツー ピア アクティビティ レポートをビジネスの Skype](peer-to-peer-activity-report.md)ユーザーに IM、音声/ビデオ、アプリケーションの共有とファイルの転送を使用している量を表示できます。
    
- [Skype for Business PSTN の使用状況レポート](pstn-usage-report.md)分数で受信/送信の通話時間し、これらの呼び出しのコストを表示できます。

- [Skype for Business PSTN 分プール レポート](pstn-minute-pools-report.md)は、組織内の現在の月の中に使用される時間を分単位で表示できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md)個々 のユーザーの通話エクスペリエンスの詳細を表示できます。
   
## <a name="related-topics"></a>関連トピック
[Office 365 管理センターでのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
