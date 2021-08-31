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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: 'このレポートは、他のSkype for Businessレポートと共に、組織全体での PSTN の使用状況など、アクティビティの詳細を示します。 '
ms.openlocfilehash: c88614d4ca7745f972f42b9fcf19a2858a1c6992
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732286"
---
# <a name="users-blocked-report"></a>ブロックされているユーザーのレポート

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

新しい [Skype for Business **レポート]** ダッシュボードには、組織内の製品全体Skype for Businessアクティビティの概要が表示されます。 これにより、個々の製品レベルのレポートにドリルダウンして、各製品内のアクティビティに関するより詳細な分析情報を提供できます。 たとえば、ユーザーのブロックSkype for Businessを使用して、PSTN 通話がブロックされている組織内のユーザーを確認できます。 このレポートは、他のSkype for Businessレポートと共に、組織全体での PSTN の使用状況など、アクティビティの詳細を示します。
  
 利用可能なその他のレポートについては、[レポートの概要](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)を確認してください。
  
> [!NOTE]
> 管理者として管理者としてサインインSkype for Business、すべてのレポートを表示Microsoft 365 管理センター。 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>ユーザーがブロックされているレポートSkype for Businessアクセスする方法

![ロゴのアイコンSkype for Business表示されます。](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

- 管理センターに移動し、[管理センター] **>[**  >  **ユーザー Skype for Businessブロック]**  >    >  **をクリックします**。
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>ユーザーがブロックSkype for Businessレポートを解釈する

表示される各列を見て、ブロックされたユーザーにビューを表示できます。
  
レポートは、このように表示されます。 
  
![ブロックされたユーザー レポート。](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

次の表は、通話をブロックしているすべてのユーザーの内訳を示しています。 これにより、電話会議または電話会議電話システム割り当てられているすべてのユーザーが表示されます。 表では、列を追加したり、削除したりすることができます。
***
![数値 1。](../images/sfbcallout1.png)
*   **ユーザー ID** は、ユーザーのサインインです。
*   **電話は**、ユーザーに割り当てられている番号です。 
*   **ブロック アクション時間は** 、ユーザーが呼び出しをブロックされた時刻 (UTC) です。
*   **ブロック アクション** は、ユーザーをブロックするために実行されたアクションの種類です。
*   **ブロック アクションの理由** は、ユーザーが呼び出しをブロックされた理由です。
***
![数値 2。](../images/sfbcallout2.png)<br/>
1 つ以上の列の全データをまとめたビューを作成したい場合は、列を [ **特定の列を基準にグループ化するには、ここに列ヘッダーをドラッグ アンド ドロップします**] にクリック アンド ドラッグします。
***
![数値 3.](../images/sfbcallout3.png)<br/>
また、[ **Excel にエクスポート**] をクリックまたはタップして、レポート データを Excel の .csv ファイルにエクスポートすることもできます。

これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2,000 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行います。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Skype for Business のその他のレポートを表示しますか?

- [Skype for Business アクティビティ レポート](activity-report.md) - ユーザーがどの程度ピアツーピア、開催、参加で電話会議セッションを使用しているかを確認できます。
    
- [Skype for Business クライアントの使用レポート](device-usage-report.md) - Windows ベースのオペレーティング システムとモバイル デバイスを含む、Skype for Business アプリがインストールされていて IM と会議に使用されるデバイスを確認できます。
    
- [Skype for Business 電話会議開催者アクティビティ レポート](conference-organizer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、Web、ダイヤルイン/アウト - サード パーティ、ダイヤルイン/アウト - Microsoft を使用した電話会議を開催しているかを確認できます。
    
- [Skype for Business参加者アクティビティ レポートを作成する](conference-participant-activity-report.md)参加している IM、音声/ビデオ、アプリケーション共有、Web 会議、ダイヤルイン/アウト会議の数を確認できます。
    
- [Skype for Business ピアツーピア アクティビティ レポート](peer-to-peer-activity-report.md) - ユーザーがどの程度 IM、音声/ビデオ、アプリケーション共有、ファイル転送を使用しているかを確認できます。
    
- [Skype for Business PSTN 利用状況レポート](pstn-usage-report.md)受信/送信呼び出しに費やされた分数と、これらの呼び出しのコストを確認できます。

- [Skype for Business PSTN の利用分数プール レポート](pstn-minute-pools-report.md) - 組織内で今月中に消費された分数を確認できます。

- [Skype for Business セッションの詳細レポート](session-details-report.md) - 個々のユーザーの通話体験に関する詳細を確認できます。
   
## <a name="related-topics"></a>関連トピック
[管理センターのアクティビティ レポート](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
