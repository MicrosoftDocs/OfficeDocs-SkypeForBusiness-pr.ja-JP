---
title: OneDrive for Business と SharePoint Online を使用して会議の記録を行う
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で Stream から OneDrive for Business および SharePoint 会議の記録ストレージに切り替える方法について説明します。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506326"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>OneDrive for Business と SharePoint Online または Stream を使用して会議の記録を行う

> [!Note]
> Microsoft Stream から会議の記録用の OneDrive for Business および Microsoft SharePoint Online への変更は段階的なアプローチになります。

|<div style="width:290px">日付&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |イベント&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020 年 10 月 5 日<br> *Complete* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| [Teams の会議ポリシー] を有効にすると、Microsoft Stream (クラシック) の代わりに OneDrive for Business と SharePoint Online に会議の記録を保存します|
|2021 年 1 月 7 日より開始<br> *Complete* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|組織の Teams 会議ポリシーを変更し、それを明示的に **Stream** に設定することで、この変更を後回しにしない限り、すべての新しい Teams 会議の記録を OneDrive for Business と SharePoint Online に保存します。 Stream をポリシーで報告するだけでは十分ではありません。 ポリシー値を明示的に **Stream** に設定する必要があります。|
|2021年 1 月 11 日より開始<br> *Complete* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC のみ**<br> GCC をご利用のお客様は、10 月 5 日からオプトアウトすることはできますが、オプト インすることはできません。 この機能は、(オプトアウト) を使用していない場合、2021 年 1 月 11 日以降のすべての GCC ユーザーにロールアウトされます。<br>  <br>2021 年 1 月 11 日から、GCC をご利用のお客様は、組織の Teams 会議ポリシーを変更し、それを明示的に **Stream** に設定することによって、この変更を遅らせない限りは、Teams の会議記録はすべて OneDrive for Business と SharePoint Online に保存されます。 <br><br>オプトアウトしても、この機能を有効にする準備ができたら、Teams の会議ポリシーを明示的に **OneDrive for Business** に設定することで、この機能を有効にすることができます。 |
|2021 年 3 月 1 日からロールアウト開始<br> *(完了)* 　&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High および DoDのみ**<br> お客様は Microsoft Teams で初めてクラウド会議の記録を有効にできるようになりました。 これらの録画は既定で OneDrive および SharePoint Online に保存され、再生されます。 |
|2021 年 7 月 7 日よりロール アウト開始<br> *(完了)* 　&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**すべてのお客様 (エンタープライズ、教育、GCC)**<br> OneDrive と SharePoint Online に記録され、会議中にライブで文字起こしされた Teams 会議の場合、Microsoft Search で検索し、文字起こしに基づいて会議の記録ファイルを見つけることができるようになりました。 |
|2021 年 8 月 16 日から段階的に展開します &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**すべてのお客様 (エンタープライズ、教育、GCC)**<br>Microsoft Stream (クラシック) には、新しい会議の記録を保存できません。Teams 会議ポリシーを Stream に変更した場合でも、すべての顧客は会議の記録を OneDrive for Business と SharePoint Online に自動的に保存します。<br><br> 組織の変化をより効果的に管理するために、変更が可能になるまで待つよりも、変更するのが都合が良いタイミングでオプト インすることをお薦めします。 |

Microsoft Teams には、会議の記録を保存するための新しい方法があります。 従来の Microsoft Stream から[新しい Stream](/stream/streamnew/new-stream) への移行の最初のフェーズとして、このメソッドは Microsoft 365 の Microsoft OneDrive for Business と SharePoint Online に記録を保存し、多くの利点を提供します。

Stream (クラシック) は、近い将来プラットフォームとして廃止の予定はありません。 現在 Stream (クラシック) に存在するビデオは、OneDrive および SharePoint Online に移動するための将来の移行ツールが利用可能になるまで、そこにとどまります。 今後の計画の詳細については、「[Stream クラシックの移行](/stream/streamnew/classic-migration)」を参照してください。

> [!NOTE]
> Teams 会議の記録を OneDrive/SharePoint Online に正常にアップロードできない場合、記録は Azure Media Services (AMS) に一時的に保存されます。 AMS に保存すると、記録を OneDrive/SharePoint Online または Stream に自動的にアップロードするための再試行は行われなくなります。

AMS に保存されている会議の記録は、自動的に削除される前に 21 日間使用できます。 コピーを保持する必要がある場合、ユーザーは AMS からビデオをダウンロードできます。

記録の保存に OneDrive for Business と SharePoint Online を使用すると、次のような利点があります。

- Teams 会議記録 (TMR) (S + C E5 自動保持ラベル) 用アイテム保持ポリシー
- OneDrive for Business と SharePoint Online 情報ガバナンスの恩恵を受ける
- アクセス許可と共有を簡単に設定
- 明示的な共有のみを使用してゲスト (外部ユーザー) とレコーディング を共有する
- アクセス フローを要求する
- OneDrive for Business と SharePoint Online 共有リンクを提供する
- 会議の記録をより早く使用できるようにする
- 会議に記録された検索基準のトランスクリプト
- **ローカルにする** テナントへのサポート
- 複数地域のサポート – 記録はそのユーザーに固有の地域に格納されます。
- 独自のキー (BYOK) サポートを利用する

「[現在使用可能な機能と今後期待される機能](/stream/streamnew/features-new-version-stream)」 の全リストをご覧ください。

詳細については、「Microsoft Teams 会議の記録の新機能」を参照してください。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business と SharePoint Online の会議の記録オプションをセットアップする

[会議の記録] オプションは、チーム ポリシー レベルの設定です。 次の例では、グローバル ポリシーの設定方法を示しています。 ユーザーに割り当てたポリシーに対して、[会議の記録] オプションが設定されていることを確認します。

> [!Note]
> Teams の会議ポリシー変更の反映にはしばらく時間がかかります。設定してから数時間後に再び確認し、サインアウトしてから、Teams デスクトップ アプリにもう一度サインインするか、コンピューターを再起動します。

1. Teams PowerShell PowerShell をインストールします。

   > [!NOTE]
   > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。 「[PowerShell を使用する Skype for Business Online を管理する](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)」を参照してください。

2. 管理者として Windows PowerShell を開きます。

3. [Teams PowerShell モジュール](./teams-powershell-install.md)をインストールします。

4. MicrosoftTeams モジュールをインポートし、Teams 管理者としてサインインします。

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) を使用して、Teams の会議ポリシーを設定し、Stream ストレージから OneDrive for Business と SharePoint Online に切り替えます。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> ユーザーの中に、開催者単位またはユーザー単位のポリシーが割り当てられているユーザーがいる場合は、ポリシーのこの設定を設定して、OneDrive for Business と SharePoint Online で会議の記録を保存できるようにする必要があります。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)」を参照してください。

## <a name="learn-more"></a>詳細情報

Teams のクラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。 その記事では、記録のセットアップ、管理、ガバナンス、アクセス許可、およびストレージについて詳しく知ることができます。
