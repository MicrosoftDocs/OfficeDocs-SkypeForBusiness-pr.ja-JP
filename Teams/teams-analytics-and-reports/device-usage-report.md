---
title: Microsoft Teams のデバイス使用状況レポート
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターの Teams デバイス使用状況レポートを使用して、組織内のユーザーが Teams に接続する方法を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033805"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams のデバイス使用状況レポート

Microsoft Teams 管理センターの Teams デバイス使用状況レポートには、ユーザーが Teams に接続する方法に関する情報が表示されます。 レポートを使用すると、外出先でモバイル デバイスから Teams を使用する数など、組織全体で使用されているデバイスを確認できます。  

## <a name="view-the-device-usage-report"></a>デバイス使用状況レポートを表示する


Teams 管理センターでレポートを表示するには、グローバル管理者、グローバル 閲覧者、または Teams サービス管理者である必要があります。 「[Teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。


1. Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。 [ **レポートの表示** ] タブの [ **レポート**] で、[ **Teams デバイスの使用状況**] を選択します。
2. **[日付の範囲]** で範囲を選択し、**[レポートの実行]** をクリックします。

    ![吹き出しが表示された Teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット。](../media/teams-reports-device-usage-with-callouts.png "Teams 管理センターの Teams デバイス使用状況レポートのスクリーンショット (吹き出しあり)")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |Teams デバイスの使用状況レポートは、過去 7 日間、30 日、90 日、180 日間の傾向を確認できます。  |
|**2**   |各レポートには、レポートが生成された日付があります。 通常、レポートには、アクティビティの時点から 24 時間から 48 時間の待機時間が反映されます。 |
|**3**   |<ul><li>グラフの X 軸は、Teams への接続に使用されるさまざまなデバイス (**Windows**、 **Mac**、 **Linux**、 **iOS**、 **Android Phone**、 **Web**) を表します。 </li><li>Y 軸は、選択した期間にデバイスを使用しているユーザーの数です。</li> </ul>デバイスを表すバーにマウス ポインターを合わせると、デバイスを使用して Teams に接続するユーザーの数が表示されます。|
|**4**   |この表では、ユーザー別のデバイス使用量の内訳を示します。 <ul><li>**ユーザー名** は、ユーザーの表示名です。 表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。 </li><li>**ユーザーが Windows** ベースのコンピューター上の Teams デスクトップ クライアントでアクティブであった場合、Windows が選択されます。</li><li>**ユーザーが macOS** コンピューター上の Teams デスクトップ クライアントでアクティブであった場合、Mac が選択されます。 </li> <li>**Linux** コンピューター上の Teams デスクトップ クライアントでユーザーがアクティブであった場合、Linux が選択されます。 </li> <li>**ユーザーが iOS** 用 Teams モバイル クライアントでアクティブであった場合、iOS が選択されます。</li><li>ユーザーが Android 用 Teams モバイル クライアントでアクティブであった場合、**Android スマートフォン** が選択されます。</li><li>**ユーザーが ChromeOS** コンピューター上の Teams デスクトップ クライアントでアクティブであった場合、Chrome OS が選択されます。</li><li>ユーザーが Teams **Web** クライアントでアクティブであった場合、Web が選択されます。 <li>**[最後のアクティビティ]** は、ユーザーが Teams アクティビティに参加した最後の日付 (UTC) を指します。</li> </ul> ユーザー アカウントが Azure AD に存在しなくなった場合は、ユーザー名がテーブルに "--" として表示されます。 <br><br>表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。 |
|**6**   |オフライン分析のためにレポートを CSV ファイルにエクスポートします。 **[Excel にエクスポート**] アイコンを選択すると、ブラウザー内でレポートがダウンロードされます。|
|**7** |上のグラフで表される時系列データは、テナント全体に対して集計されたさまざまな使用状況メトリックを示しています|
|**8** |ボットンの半分に表される表形式のデータは、ユーザーごとに集計されたさまざまな使用状況メトリックを示しています|


## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

Teams ユーザー アクティビティ レポートのデータを匿名にするには、グローバル管理者である必要があります。 グローバル管理者は、レポート内の表示名、グループ名、電子メール、AAD ID などの識別可能な情報 (MD5 ハッシュを使用して) を非表示にできます。

1. Microsoft 365 管理センターで、[設定 **組織の設定]** \> に移動し、[**サービス**] タブで [レポート] を選択 **します**。
    
2. [ **レポート]** を選択し、 **すべてのレポートで非表示のユーザー名、グループ名、サイト名を表示** するを選択します。 この設定は、Microsoft 365 管理センターの使用状況レポートと Teams 管理センターの両方に適用されます。
  
3. [ **変更の保存] を選択します**。

> [!NOTE]
> この設定を有効にすると、 [Teams ユーザー アクティビティ レポート](user-activity-report.md)、 [Teams デバイス使用状況](device-usage-report.md)レポート、Teams 使用状況レポートのユーザー、グループ、サイト名の情報 [が](teams-usage-report.md)識別されなくなります。 2021 年 9 月 1 日から、この設定は、重要な情報を保護し、企業が地域のプライバシーに関する法律をサポートできるようにするための継続的な取り組みの一環として、すべてのユーザーに対して既定で有効になっています。 
>
>この設定は、Microsoft 365 管理センター、Microsoft Graph、および Power BI の Microsoft 365 使用状況レポートにも適用されます。

## <a name="related-topics"></a>関連項目

- [Teams の分析とレポート](teams-reporting-reference.md)
