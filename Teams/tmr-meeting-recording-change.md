---
title: 会議OneDrive for Businessに SharePoint Online を使用する
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: '[ストリーム] から [オンライン] に切りOneDrive for Business、SharePointのオンライン会議記録ストレージに切り替えるMicrosoft Teams。'
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486137"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>会議の記録OneDrive for BusinessオンラインSharePointストリームを使用する

> [!Note]
> Microsoft Stream の使用から会議の記録OneDrive for BusinessおよびMicrosoft Office SharePoint Onlineへの変更は、段階的なアプローチになります。

|<div style="width:290px">日付&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |イベント&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020 年 10 月 5 日<br> *Complete* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Teams 会議ポリシーを有効にして、Microsoft Stream (クラシック) の代わりに OneDrive for Business に保存し、SharePoint Online に保存します。|
|2021 年 1 月 7 日より開始<br> *Complete* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|組織の Teams 会議ポリシーを変更し、明示的に [ストリーム] に設定してこの変更を遅らせない限り、すべての新しい Teams 会議記録は OneDrive for Business および SharePoint Online に保存 **されます**。 Stream をポリシーで報告するだけでは十分ではありません。 ポリシー値を明示的に **Stream** に設定する必要があります。|
|2021年 1 月 11 日より開始<br> *Complete* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC のみ**<br> GCC をご利用のお客様は、10 月 5 日からオプトアウトすることはできますが、オプト インすることはできません。 この機能は、(オプトアウト) を使用していない場合、2021 年 1 月 11 日以降のすべての GCC ユーザーにロールアウトされます。<br>  <br>2021 年 1 月 11 日から、組織の Teams 会議ポリシーを変更し、明示的に [ストリーム] に設定してこの変更を遅らせない限り、GCC のお客様の新しい Teams 会議記録はすべて OneDrive for Business と SharePoint Online に保存 **されます。** <br><br>オプトアウトしても、この機能を有効にする準備ができたら、Teams の会議ポリシーを明示的に **OneDrive for Business** に設定することで、この機能を有効にすることができます。 |
|2021 年 3 月 1 日からロールアウト開始<br> *(完了)* 　&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC High および DoDのみ**<br> お客様は Microsoft Teams で初めてクラウド会議の記録を有効にできるようになりました。 これらの録音は、既定では、OneDrive Online SharePoint保存および再生されます。 |
|2021 年 7 月 7 日よりロール アウト開始 <br> *(完了)* 　&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**すべてのお客様 (エンタープライズ、教育、GCC)**<br> OneDrive と SharePoint Online に記録され、会議中にライブで文字起こしされた Teams 会議の場合は、Microsoft Search で検索して、トランスクリプトに基づいて会議記録ファイルを検索できます。 |
|2021 年 8 月 16 日から段階的に展開する &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**すべてのお客様 (エンタープライズ、教育、GCC)**<br>新しい会議のレコーディングを Microsoft Stream (クラシック) に保存できません。すべてのお客様は、OneDrive for Business および SharePoint Online に保存された会議の記録を、Teams 会議ポリシーを Stream に変更した場合でも自動的に保持されます。<br><br> 組織の変化をより効果的に管理するために、変更が可能になるまで待つよりも、変更するのが都合が良いタイミングでオプト インすることをお薦めします。 |

Microsoft Teams には、会議の記録を保存するための新しい方法があります。 従来の Microsoft Stream から新しいストリームへの移行[](/stream/streamnew/new-stream)の第 1 フェーズとして、このメソッドは Microsoft 365 の Microsoft OneDrive for Business と SharePoint Online に記録を格納し、多くの利点を提供します。

プラットフォームとしてのストリーム (クラシック) は、近い将来非推奨になる予定です。 現在 Stream (クラシック) に保存されているビデオは、将来の移行ツールを使用して、OneDrive に移行し、SharePointします。 今後の [プランの詳細については、](/stream/streamnew/classic-migration) クラシック移行のストリーム配信に関するページを参照してください。

> [!NOTE]
> Teams会議の記録が OneDrive/SharePoint Online に正常にアップロードできない場合、記録は一時的に Azure Media Services (AMS) に保存されます。 AMS に格納された後は、オンラインまたはストリームの OneDrive/SharePointに記録を自動的にアップロードする再試行は行われます。

AMS に保存されている会議の記録は、自動的に削除される前に 21 日間使用できます。 コピーを保持する必要がある場合、ユーザーは AMS からビデオをダウンロードできます。

記録を保存するために OneDrive for Business Online SharePoint使用する利点は次のとおりです。

- Teams 会議記録 (TMR) (S + C E5 自動保持ラベル) 用アイテム保持ポリシー
- オンライン情報ガバナンスOneDrive for BusinessとSharePointの利点
- アクセス許可と共有を簡単に設定
- 明示的な共有のみを使用してゲスト (外部ユーザー) とレコーディング を共有する
- アクセス フローを要求する
- オンライン共有OneDrive for BusinessリンクSharePointとリンクを提供する
- 会議の記録をより早く使用できるようにする
- 会議に記録された検索ベースのトランスクリプト
- **ローカルにする** テナントへのサポート
- 複数地域のサポート – 記録はそのユーザーに固有の地域に格納されます。
- 独自のキー (BYOK) サポートを利用する

「[現在使用可能な機能と今後期待される機能](/stream/streamnew/features-new-version-stream)」 の全リストをご覧ください。

詳細については、「Microsoft Teams 会議の記録の新機能」を参照してください。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business Online の会議SharePoint設定する

[会議の記録] オプションは、チーム ポリシー レベルの設定です。 次の例では、グローバル ポリシーの設定方法を示しています。 ユーザーに割り当てたポリシーに対して、[会議の記録] オプションが設定されていることを確認します。

> [!Note]
> Teams の会議ポリシー変更の反映にはしばらく時間がかかります。 設定してから数時間後に再び確認し、サインアウトしてから、Teams デスクトップ アプリにもう一度サインインするか、コンピューターを再起動します。

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

5. [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)を使用して、Teams 会議ポリシーを設定して、Stream ストレージから OneDrive for Business および SharePoint Online に移行します。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 一部のユーザーが開催者またはユーザーごとのポリシーを割り当てている場合は、OneDrive for Business および SharePoint Online にも会議の記録を保存する場合は、このポリシーにこの設定を設定する必要があります。 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)」を参照してください。

## <a name="learn-more"></a>詳細情報

クラウド会議の記録の詳細Teams、クラウド会議の記録に関するTeams[を参照してください](cloud-recording.md)。 この記事では、セットアップ、管理、ガバナンス、アクセス許可、ストレージの記録の詳細について説明します。
