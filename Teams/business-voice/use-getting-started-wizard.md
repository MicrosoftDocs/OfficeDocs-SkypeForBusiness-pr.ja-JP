---
title: '[作業の開始] ウィザードを使用して Business Voice をセットアップする'
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e6ed778af0136516286798b0a7b04602f571de2
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653533"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>[作業の開始] ウィザードを使用して Business Voice をセットアップする

Microsoft 365 Business Voice の [作業の開始] ウィザードを使用すると、Microsoft Teams で電話の受信と発信を簡単かつ迅速に開始できます。 始めたばかりの小規模ビジネスの場合、ウィザードを使用すると、電話番号、通話メニュー、案内応答などを使用して、数分で起動して実行できます。 テレフォニー ソリューションを確立している大企業の場合、ウィザードを使用して Business Voice パイロットをセットアップできるため、すべてのユーザーにセットアップする前に少数のユーザーで試用できます。 いずれにしても、ウィザードが終了したらすぐに Business Voice の使用を開始できます!

ウィザードを開始する前にこの記事を読むことをお勧めします。 準備ができたら、「[Microsoft 365 Business を使い始める](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice)」のページの [**作業の開始**] を選択して、ウィザードを開くことができます。 サブスクリプションの作成に使用したアカウントまたはグローバル管理者である別のアカウントでサインインしてください。

> [!IMPORTANT]
> Business Voice は現在、カナダとイギリスで利用できます。 2020 年にはさらに多くの国と地域で利用可能になります。
>
> Microsoft Teams と Business Voice は、ユーザーのメールボックスが Microsoft 365 にある場合にのみ機能します。  オンプレミスの Exchange サーバーにあるメールボックスはサポートしていません。

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a>緊急サービスの場所

<table>
    <tr>
        <td>緊急アドレスを変更する場合は、[<b>編集</b>] をクリックして新しいアドレスを入力します。 入力したアドレスは、正当なものであり、緊急対応サービス用に正しく書式設定されていることを確認するために検証されます。 有効な場合、次の手順で番号を割り当てるすべてのユーザーにアドレスが割り当てられます。 複数の場所に従業員がいる場合、「Business Voice のカスタマイズ」トピックでは、[作業の開始] ウィザードの完了後に緊急アドレスを追加して割り当てる方法を示します。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

詳細については、「[緊急対応の場所、アドレス、通話ルーティングの概要](../what-are-emergency-locations-addresses-and-call-routing.md)」をご覧ください。

## <a name="company-phone-number"></a>会社の電話番号

<table>
    <tr>
        <td>新しい電話のローカル電話番号を設定することに加えて、フリーダイヤル番号を購入するか、既存の番号を Microsoft 365 にポートするかを選択できます。 フリーダイヤル番号を設定する場合は、通話プランを購入する必要があります。 複数の番号を Microsoft 365 にポートする場合は、ウィザードの完了後に [Teams 管理センター](https://admin.teams.microsoft.com)でポートを行うオプションがあります。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 既存の電話番号を Microsoft 365 にポートしようとしても、ウィザードにはそのまま一時的な電話番号が表示されます。 これは問題ありません。 ウィザードを完了し、ポート プロセスを完了すると、一時的な電話番号が電話番号に置き換えられます。

## <a name="assigning-licenses-to-users"></a>ユーザーにライセンスを割り当てる

<table>
    <tr>
        <td>Teams の外部で電話を発信および受信する組織内の人を選択します (サプライヤーへの電話など)。 使用可能な Business Voice ライセンスの数まで選択できます。 さらに必要な場合は、ウィザードの終了時に追加のライセンスを購入できます。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> 個々のユーザーの既存の電話番号を Microsoft 365 にポートする場合は、ウィザードの完了後に行うことができます。 ポート プロセスを完了すると、ウィザードで選択された一時的な電話番号が、ポートされた電話番号に置き換わります。

## <a name="incoming-call-greeting"></a>着信の案内応答

<table>
    <tr>
        <td>案内応答として使用する最大 5 メガバイト (MB) の音声ファイル (MP3 または WAV) をアップロードするか、案内応答を入力すると、Microsoft 365 は音声合成を使用して発信者に読み上げます。 案内応答は、発信者が会社の電話番号に電話をかけるときに最初に聞くことになります。 正しい発音のために、単語のスペルを間違えたり、音声表記を使用する必要がある場合があります。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>通話メニューと転送

<table>
    <tr>
        <td>すべての通話を特定のユーザーに転送するか、ユーザーがオプションを選択できる通話メニューを設定できます。 通話メニューを作成する場合、電話のキーパッドで数字を押すか、音声コマンドでオプションを話すことで、発信者が選択できるオプションを指定できます。 各メニューのオプションは 1 人のユーザーに転送できます。 <br>
        発信者に指示する最大 5MB の音声ファイル (MP3 または WAV) をアップロードするか、指示を入力するかを選択できます。 Microsoft 365 は、音声合成を使用して、発信者への指示を読みます。 正しい発音のために、音声で単語を綴る必要がある場合があります。
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> [作業の開始] ウィザードを使用すると、すぐに起動して実行できるシンプルな通話メニューを設定できます。 通話メニューを設定する複数の電話番号がある場合、またはより複雑な (自動応答とも呼ばれる) 通話メニューを設定する場合は、ウィザードの終了後、「[クラウドの自動応答をセットアップする](set-up-auto-attendants.md)」の手順に従って設定できます。

<table>
    <tr>
        <td> <p>[<b>概要</b>] ページの [作業の開始] ウィザードは、入力したすべてのものを取得し、Business Voice をセットアップします。 ユーザーに割り当てられる電話番号を確認したり、通話メニューを確認したり、案内応答を聞いたりすることができます。 </p>
             <p>Business Voice のセットアップには数分かかります。 [<b>完了</b>] をクリックすると、引き続き Business Voice をバックグラウンドでセットアップするか、完了するまで待つことができます。 完了したら、<a href="https://admin.teams.microsoft.com" target="_blank">Teams 管理センター</a>の [<b>音声</b>] に移動して、さらに Business Voice 機能をセットアップします。</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>