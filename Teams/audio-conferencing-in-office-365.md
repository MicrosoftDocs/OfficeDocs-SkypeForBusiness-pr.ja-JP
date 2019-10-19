---
title: Office 365 における電話会議
ms.author: tonysmit
author: tonysmit
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
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.overview
ms.custom:
- Audio Conferencing
ms.openlocfilehash: cf8aa0de368803fa957667e239ba6ed0b161c0cb
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37517045"
---
# <a name="audio-conferencing-in-office-365"></a>Office 365 における電話会議
Office 365 の電話会議では、ユーザーは自分の電話から会議にダイヤルインすることができます。 電話会議には最大で250の電話出席者が参加できます。

## <a name="what-is-audio-conferencing"></a>電話会議とは何ですか?
会議への通話 (ダイヤルイン) は、外出先でも、ノート pc やモバイルデバイスで Skype for Business または Microsoft Teams アプリを使って会議に参加することはできません。 ただし、電話を使って Skype for Business 会議または Microsoft Teams 会議に参加する場合は、コンピューター上のアプリを使用するよりも便利な方法があります。
  
- インターネット接続は制限されています。
- 会議は音声のみである。
- このユーザーは Skype for Business 会議に参加しようとして失敗しました。
- 発信時に通話音質が良くなります。
- ユーザーは、Bluetooth デバイスを使って "ハンズフリー" で会議に参加できます。
- ユーザーは、状況に応じて、より簡単で便利な検索を行うことができます。

電話会議の設定は、会議のスケジュールを設定または会議を進行するユーザーに対してのみ必要です。ダイヤルインで参加するユーザーについては、ライセンスの割り当てや他の設定は必要ありません。

出席者が会議に参加したら、ダイヤルアウトして、他の発信者を Skype for Business または Microsoft Teams の会議に招待することもできます。 他のユーザーが会議に参加したり、 [Skype For business 会議からダイヤルアウトして他の](/SkypeForBusiness/audio-conferencing-in-office-365/dialing-out-from-a-meeting-so-other-people-can-join-it)ユーザーが参加できるようにするには、「 [Teams 会議からダイヤルアウト](dialing-out-from-a-teams-meeting-so-other-people-can-join-it.md)する」を参照してください。

## <a name="what-does-it-cost"></a>料金について教えてください。
価格情報については、「[電話会議の価格](https://products.office.com/skype-for-business/audio-conferencing#Requirements)」を参照してください。

## <a name="where-is-it-available"></a>どこで利用できますか?
電話会議を使用すると、ユーザーは有料電話番号と無料電話番号を使って会議にダイヤルインすることができます。 電話会議が有効になっている場合、有料 (サービス) 番号は、組織に共有電話会議番号として自動的に割り当てられます。 専用の有料電話番号および無料電話番号は、追加の都市から組織に割り当てることができます。

無料電話番号 (サービス番号) は利用できますが、一部の国/地域でのみ使用できます。 お住まいの国または地域で利用可能な機能については、「[電話会議と通話プランの国と地域の空き時間](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)情報」を参照してください。

組織の電話会議を使用することにした場合は、電話会議をスケジュール/主催しようとしている組織内の各ユーザーに対して、1つの**電話会議**ライセンスを購入する必要があります。

## <a name="how-do-conferencing-bridges-work"></a>会議ブリッジはどのように動作しますか?
Skype for Business または Microsoft Teams の電話会議をセットアップしているときに、電話会議ブリッジを利用できます。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Skype for Business および Microsoft Teams アプリの会議の招待に含まれます。 [電話会議ブリッジの電話番号を変更](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)することができます。また、[その他の電話会議ブリッジの設定を変更](change-the-settings-for-an-audio-conferencing-bridge.md)することもできます。 
  
電話会議ブリッジは、電話を使って会議にダイヤルインしているユーザーに対して、通話に応答します。 自動応答からの音声プロンプトによって発信者に応答し、設定に応じて通知を再生して、発信者に名前を記録するように依頼することができます。 **Microsoft bridge の設定**では、会議の通知と会議の参加エクスペリエンスの設定を変更したり、 [Microsoft Teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)または[Skype for business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings)の会議の開催者によって使用される pin の長さを設定したりすることができます。 会議の開催者が Skype for Business または Microsoft Teams アプリを使って会議に参加できない場合は、Pin を使って会議を開始します。

## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>電話会議ブリッジで設定されたダイヤルイン電話番号
会議ブリッジに割り当てることができる電話会議の電話番号には、**共有**と**専用**の2種類があります。 どちらの番号も、任意の発信者が組織内の電話会議に参加するために使用できます。
  
 **専用電話番号** とは、組織内のユーザーだけが使用できる電話番号のことです。 誰かがこれらの番号のいずれかに電話をかけるときに使用する言語を変更できます。 これらのサービス用の電話番号を取得する必要があります。
  
 **共有電話番号** とは、他の Office 365 組織と共有できる電話番号です。誰かがこれらの番号のいずれかに通話するときに使用する言語は変更できません。
  
開催者に割り当てられている既定の電話会議番号は、会議出席依頼にのみ含まれていますが、発信者は会議に参加するために、会議ブリッジに割り当てられている電話番号を使うことができます。 会議に参加するために使用する電話番号の一覧はそれぞれの会議の招待状に含まれる [ **電話番号の検索**] リンクを使用して利用できます。

詳細については、「 [Microsoft Teams の電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md)」または「 [Skype for Business Online の電話会議の電話番号](/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)」を参照してください。
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自動的に割り当てられた電話会議の電話番号
共有電話会議の電話番号は、電話会議が有効になっている場合、組織に自動的に割り当てられます。 電話番号が割り当てられる場合、電話番号は会議ブリッジの既定の電話番号として割り当てられます。 ブリッジの既定の番号として割り当てられた電話番号は、組織の国/地域のものです。
  
> [!NOTE]
> 組織の国または地域の場所は、 **Microsoft 365 管理センター**にサインインし、[**組織プロファイル**] の下に表示されていることがわかります。 
  
> [!CAUTION]
> この国/地域の組織の有料電話番号の利用には制限があるため、これらの国/地域の組織では、電話会議の有料電話番号が自動的に割り当てられることはありません。 これらの場所からの無料電話番号は、利用可能なインベントリに応じて利用可能になります。 
  
電話番号が組織に自動的に割り当てられている国や地域のリストを確認するには、「[電話会議と通話プランを使用できる国および地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)」を参照してください。
  
## <a name="how-do-you-get-dedicated-phone-numbers"></a>専用の電話番号を取得するには、どうすればよいですか?
専用の電話会議の電話番号は、お客様が取得して組織に割り当てることができるサービス番号です。 次の3つの方法のいずれかで、電話会議用に専用の有料電話番号と無料電話番号を取得できます。

- **Skype for Business 管理センターを使用する。** 一部の国/地域では、Skype for Business 管理センターを使って、会議ブリッジの番号を取得できます。 「[サービスの電話番号を取得](/microsoftteams/getting-service-phone-numbers)する」をご覧ください。
    
- **既存の番号を移行する。** 既存の番号を現在のサービス プロバイダーまたは電話会社から Office 365 に移行または転送します。 詳細については、[電話番号を Office 365 に移行する](transfer-phone-numbers-to-office-365.md) または [組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) を参照してください。  
  
- **新しい番号には申請書を使用します。** 国または地域によっては Skype for Business 管理センターを使用して新しい電話番号を取得することが出来ない場合があります。または、特定の電話番号またはエリアコードが必要です。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 」を参照してください。

## <a name="how-do-you-set-it-up"></a>設定方法を教えてください。
ユーザーに対して電話会議をセットアップする場合は、「 [Microsoft Teams の電話会議をセットアップ](set-up-audio-conferencing-in-teams.md)する」または「 [Skype for business Online の電話会議](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)をセットアップする」を参照してください。

## <a name="related-topics"></a>関連トピック

[Skype for Business Online をセットアップする](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
  
[Microsoft Teams での電話会議の電話番号](phone-numbers-for-audio-conferencing-in-teams.md) 

[Skype for Business Online の電話会議の電話番号](/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)
