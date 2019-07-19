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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 'このレポートと他の Skype for Business レポートを使用すると、組織全体の PSTN 利用状況などのアクティビティについて詳しく知ることができます。 '
ms.openlocfilehash: 95269dc08806ab09a44f47153748d45a63fedbc2
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793016"
---
# <a name="users-blocked-report"></a>ブロックされているユーザーのレポート

新しい Skype for Business**レポート**ダッシュボードには、組織内の Skype for business 製品全体でのアクティビティの概要が表示されます。 個々の製品レベルレポートにドリルインして、各製品内のアクティビティについて、より詳細な洞察を得ることができます。 たとえば、 **Skype For business ユーザーがブロック**されたレポートを使って、PSTN 通話の発信をブロックされている組織内のユーザーを確認できます。 このレポートと他の Skype for Business レポートを使用すると、組織全体の PSTN 利用状況などのアクティビティについて詳しく知ることができます。
  
 利用可能なその他のレポートについては、 [「レポートの概要」](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)をご覧ください。
  
> [!NOTE]
> Microsoft 365 管理センターに管理者としてサインインすると、すべての Skype for Business レポートを表示できます。 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Skype for Business ユーザーがブロックされたレポートにアクセスする方法

![](../images/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン

- 管理センターに移動し >**管理** > センター**Skype for business 管理センター** > のレポート**ユーザーがブロック**された**レポート** > を表示します。
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Skype for Business ユーザーがブロックしたレポートを解釈する

表示されている各列を見ると、ブロックしたユーザーを表示できます。
  
レポートは、このように表示されます。 
  
![ブロックされたユーザレポート](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

この表には、通話の発信をブロックされているすべてのユーザーの内訳が表示されます。 これには、電話会議が割り当てられているすべてのユーザーが表示されます。 表では、列を追加したり、削除したりすることができます。
***
![ナンバー 1](../images/sfbcallout1.png)
*   **ユーザー ID**は、ユーザーのサインインです。
*   **電話番号**は、ユーザーに割り当てられている番号です。 
*   [**ブロックアクション時間**] は、ユーザーが発信をブロックされた時刻 (UTC) です。
*   **ブロックアクション**は、ユーザーをブロックするために実行されたアクションの種類です。
*   [**ブロックアクションの理由**」は、ユーザーが発信をブロックされた理由です。
***
![ナンバー 2](../images/sfbcallout2.png)<br/>
1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
***
![ナンバー 3](../images/sfbcallout3.png)<br/>
また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が2000より少ない場合は、レポート内のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype For business 電話会議参加者アクティビティレポート](conference-participant-activity-report.md)参加している IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルイン/ダイヤルアウト会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype For BUSINESS PSTN 使用状況レポート](pstn-usage-report.md)通話の着信/発信に費やした時間 (分) を確認することができます。

- [Skype For BUSINESS PSTN 分単位のプールレポート](pstn-minute-pools-report.md)には、組織内の現在の月に消費された分数が表示されます。

- [Skype For business セッションの詳細レポート](session-details-report.md)個々のユーザの通話エクスペリエンスについての詳細を見ることができます。
   
## <a name="related-topics"></a>関連トピック
[管理センターでのアクティビティレポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 