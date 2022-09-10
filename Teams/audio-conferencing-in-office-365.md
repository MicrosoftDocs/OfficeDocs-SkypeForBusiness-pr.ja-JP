---
title: Microsoft 365 の電話会議
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.assetid: a5a696c3-d321-4e61-9aad-e3a87041196e
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
- seo-marvel-apr2020
description: Microsoft 365 の電話会議で、ユーザーが自分の電話から会議に呼び出す方法について説明します。
ms.openlocfilehash: 1ac2842d219648c5a5deef0d687698cd7b5544dd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641928"
---
# <a name="audio-conferencing-in-microsoft-365"></a>Microsoft 365 の電話会議

Microsoft 365 の電話会議を使用すると、ユーザーは自分の電話から会議に通話できます。 電話会議では、最大 1,000 人の電話出席者が可能です。

## <a name="what-is-audio-conferencing"></a>電話会議とは?

会議への通話 (ダイヤルイン) は、移動中で、ノート PC やモバイル デバイスで Microsoft Teams アプリを使用して会議に出席できないユーザーにとって非常に便利です。 ただし、電話を使用して Teams 会議に出席するシナリオは、コンピューターでアプリを使用するよりも優れた方法です。
  
- インターネット接続が制限されている。
- 会議が音声のみ。
- ユーザーが Teams 会議に参加しようとしましたが、失敗しました。
- ダイヤルイン時の通話品質が優れている。
- Bluetooth デバイスを使用すると「ハンズフリー」で会議に参加できる。
- 状況によっては、そのほうが簡単で便利なことがあります。

電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。

出席者が会議に参加した後、他の発信者をダイヤルアウトして Teams 会議に招待することもできます。
詳細については、 [他のユーザーが参加できるように Teams 会議からダイヤルアウト](dialing-out-from-a-teams-meeting-so-other-people-can-join-it.md) する方法に関するページを参照してください。

## <a name="what-does-it-cost"></a>費用はいくらかかりますか?

料金については、「[電話会議の料金](https://go.microsoft.com/fwlink/?linkid=799762&clcid=0x409)」をご覧ください。

## <a name="where-is-it-available"></a>どこで利用できますか?

電話会議では、ユーザーが会議にダイヤルインするための有料電話番号と無料電話番号を使用できます。 有料 (サービス) 電話番号は、組織が電話会議を利用できるよう有効になっている場合に、共有の電話会議の電話番号として自動的に組織に割り当てられます。 専用の有料電話番号および無料電話番号は、追加の都市から組織に割り当てることができます。

無料電話番号 (サービス番号) は利用できますが、一部の国/地域でのみ利用できます。 お住まいの国または地域で何が利用可能かどうかを調べるには、「[電話会議や通話プランが利用可能な国および地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。

電話会議が組織に必要であると判断したら、**電話会議** のライセンスを、電話会議をスケジュール設定または開催する組織内のユーザーごとに 1 つずつ購入する必要があります。

## <a name="how-do-conferencing-bridges-work"></a>会議ブリッジはどのように機能しますか?

Teams の電話会議を設定すると、電話会議ブリッジが表示されます。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Teams アプリの会議出席依頼に含まれます。 [会議ブリッジの電話番号を変更したり](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)、[他の電話会議ブリッジの設定を変更したりすることもできます](change-the-settings-for-an-audio-conferencing-bridge.md)。

電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 まず自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼します。 **Microsoft ブリッジ設定** を使用すると、会議の通知と会議参加エクスペリエンスの設定を変更し、 [Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md) の会議開催者が使用する PIN の長さを設定できます。 Teams アプリを使用して会議に参加できない場合、会議の開催者は PIN を使用して会議を開始します。

## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>電話会議ブリッジで設定されたダイヤルイン電話番号

会議ブリッジに割り当てられる電話会議の電話番号には、 **共有** と **専用** の 2 種類があります。 どちらの種類の番号でも、発信者が組織内で開催される電話会議に参加するために使用できます。
  
 **専用電話番号** とは、組織内のユーザーだけが使用できる電話番号のことです。 誰かがこれらの番号のいずれかに電話をかけるときに使用する言語を変更できます。 これらのサービスの電話番号を取得する必要があります。
  
 **共有電話番号** は、他の Microsoft 365 と共有できる電話番号です。 誰かがこれらの番号のいずれかに通話するときに使用する言語は変更できません。
  
開催者に割り当てられる既定の電話会議番号は会議の招待状にのみ含まれるため、発信者は会議ブリッジに割り当てられた任意の電話番号を使用して、会議に参加できます。 会議に参加するために使用する電話番号の一覧はそれぞれの会議の招待状に含まれる [ **電話番号の検索**] リンクを使用して利用できます。

詳細については、「 [Microsoft Teams の電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md) 」を参照してください。

## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自動的に割り当てられた電話会議の電話番号

共有の電話会議の電話番号は、電話会議で有効になると組織に自動的に割り当てられます。 電話番号が割り当てられる場合、電話番号は会議ブリッジの既定の電話番号として割り当てられます。 ブリッジの既定の番号として割り当てられた電話番号は、組織の国/地域のものです。

> [!NOTE]
> 組織の国または地域の場所は、**Microsoft 365 管理センター** にサイン伸し、[**組織プロファイル**] で確認できます。

> [!CAUTION]
> ベネズエラ、インドネシアおよびアラブ首長国連邦 (UAE) では有料電話番号の利用は限られているため、これらの国/地域の組織には、電話会議の有料電話番号は自動的に割り当てられません。 これらの場所の無料電話番号は、使用可能な在庫状況に応じて利用できます。

電話番号が組織に自動的に割り当てられている国や地域のリストを確認するには、「[電話会議と通話プランを使用できる国および地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。

## <a name="how-do-you-get-dedicated-phone-numbers"></a>専用の電話番号を取得する方法を教えてください。

専用の電話会議の電話番号は、取得して組織に割り当てることができるサービス番号です。 次の 3 つの方法のいずれかで、会議ブリッジ専用の有料電話番号と無料電話番号を取得できます。

- **Teams 管理センターを使用します。** 一部の国/地域では、Teams 管理センターを使用して会議ブリッジの番号を取得できます。 「[サービス電話番号の取得](./getting-service-phone-numbers.md)」を参照してください。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは電話会社から Microsoft 365 に既存の番号を移植または転送できます。 この方法の詳細については、「[Teams に電話番号を移行](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」を参照してください。  
  
- **新しい番号には申請書を使用します。** 場合によっては (国/地域によって) Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市外局番が必要になる場合があります。 その場合は、フォームをダウンロードし、Microsoft に返送する必要があります。 詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。

## <a name="how-do-you-set-it-up"></a>設定方法を教えてください

ユーザーの電話会議を設定することに決めたら、従う必要がある手順については、「 [Microsoft Teams の電話会議を設定](set-up-audio-conferencing-in-teams.md) する」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams での電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)
