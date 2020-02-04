---
title: 'Skype for Business とサードパーティの電話会議プロバイダーとの統合の終了プログラム '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: 2021年7月31日に、サードパーティの電話会議プロバイダー (サードパーティ ACP) との Skype for Business の統合が終了すると、生涯プログラムが終了します。
ms.openlocfilehash: b9bd1640d615babab29a073aeeee2b1beb92fc02
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706692"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Skype for Business とサードパーティの電話会議プロバイダーとの統合の終了プログラム 

Microsoft は、Skype for Business とサードパーティの電話会議プロバイダー (ACPs) との統合に関して、サポート終了プログラムの開始を発表しました。 

有効期限プログラムは、2021年7月31日に終了します。 プログラムが終了すると、サードパーティの電話会議プロバイダーとの Skype for Business の統合が機能しなくなり、その日 (2021 年7月31日) に次の変更が行われます。

- サードパーティ ACP サービスによって提供されたダイヤルイン番号を使って、Skype for Business 会議に参加しようとしている参加者は、Skype for Business 会議に接続されなくなります。
 
- サードパーティ ACP サービスが有効になっているユーザーは、新しい Skype for Business 会議への招待に自動的にダイヤルイン情報を含めなくなります。

最終版プログラムの開始時のお知らせの一部として、次の変更が有効になり、終了するまで継続して使用できるようになります。 

- サードパーティ ACP サービスを使用するように構成された Skype for Business ユーザーがいない場合、サードパーティ ACP サービスを使用するようにユーザーを構成することはできません。

- サードパーティ ACP サービスを使用するように構成された Skype for Business ユーザーの既存のお客様は、有効期間が終了するまで、引き続き新しいユーザーを追加することができます。 サードパーティの ACP サービスを使用するために追加の Skype for Business ユーザーをセットアップしないことをお勧めします。2021年7月31日に変更が反映されるため、これらのサービスにも適用されます。

## <a name="preparing-for-this-change"></a>この変更の準備

この変更を準備するために、影響を受ける組織に、2021年7月31日より前にこの計画された更新のユーザーに通知するようお勧めします。 

2021年7月31日以降、ユーザーはオンライン会議を中断することなく、引き続き Skype for Business を使用することができます。ただし、組織では、Skype for Business または Microsoft Teams とのダイヤルイン音声会議が必要な場合は、Microsoft から提供された電話会議のユーザーを有効にする必要があります。 Microsoft 電話会議の詳細については、「[電話会議](https://products.office.com/en-us/skype-for-business/audio-conferencing)」を参照してください。 

組織の目的の終了状態に応じて、次の3つのパスに従うことができます。

- Microsoft 電話会議に移行します。 
- 引き続き、サードパーティの電話会議プロバイダーを個別に使用します。 
- すべてのダイヤルイン会議の使用を停止します。

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>パス #1: Microsoft 電話会議に移行する   

2021年7月31日より前に Microsoft 電話会議に移行して移行を完了すると、その日以降のサービスへの影響は発生しません。 Microsoft 電話会議への移行により、次のような変更が組織に導入されます。 

- このサービスは、他のすべての Office 365 サービスに課金されます。 

- 標準サブスクリプションを購入した場合は、有料のダイヤルイン料金がユーザーごとの月額プランの料金に含まれます。 

- 各組織とそのユーザーに、新しいダイヤルイン電話番号のセットが提供されます。 Microsoft 電話会議サービスの地理的な範囲を確認するには、「[電話会議と通話プランの国と地域の空き時間](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)情報」を参照してください。
 
- サードパーティ ACP を使って有効になっているユーザーによって既にスケジュールされている会議は、Microsoft 電話会議のダイヤルイン情報が含まれるように自動的に再スケジュールされます。
 
- 各会議の会議 Id は動的になります。つまり、各会議には専用の会議 ID があります。 動的会議 Id を使用すると、セキュリティが強化され、バックツーバック会議の操作性が向上します。

- 本サービスの使用にはすべて、電話会議サービスの利用規約が適用されます。 

Microsoft 音声会議への移行は簡単です。また、サービスのライセンスを取得した後のわずかな手順で行うことができます。 Microsoft 電話会議に移行する方法については、以下を参照してください。

- [Office 365 での電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**概要:**

- 2021年7月31日より前に Microsoft 電話会議に移行して移行を完了する組織では、その日付以降、サービスへの影響は表示されません。

- Microsoft 電話会議への移行の詳細について[は、「Office 365 で電話会議を試用または購入](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)する」を参照してください。 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>パス #2: サードパーティ電話会議プロバイダーを個別に使用し続ける

2021年7月31日以降にサードパーティ acp を引き続き使用することを決定した組織は、Skype for Business 会議のオーディオ部分に参加するためにサードパーティ ACP ダイヤルイン情報を使用できなくなるため、サービスへの影響が発生します。 

Skype for Business 会議で、一部の参加者に VoIP などの参加者を招待して、サードパーティ ACP 経由で音声を使用しないようにするには、ユーザーの会議で VoIP を無効にすることをお勧めします。 これにより、すべての参加者は、サードパーティ ACP を使って会議のオーディオ部分に参加する必要があります。会議の他のすべてのワークロード (チャットや画面共有など) は、Skype for Business で引き続きサポートされます。 

- 特定の開催者のすべての会議から VoIP を無効にするには、Set-csconferencingpolicy コマンドレットを使用して、自分の会議ポリシーの AllowIPAudio パラメーターを false に設定します。 詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
 
スケジュールの観点と2021年7月31日時点では、サードパーティ ACP のダイヤルイン情報は、Skype for Business 会議の招待に自動的に含まれなくなります。 ユーザーは、会議の一部としてこの情報を引き続き使用したい場合は、Skype for Business 会議の出席依頼にダイヤルイン情報を手動で追加する必要があります。 

2021年7月31日に、ユーザーの既存の会議が自動的に再スケジュールされ、サードパーティ ACP のダイヤルイン情報が削除されないことに注意してください。 ユーザーの会議で VoIP を有効にしておくことを決定する組織は、ユーザーに対してサードパーティ ACP の統合を無効にすることを検討してください。また、会議移行サービスを使用して、サードパーティの音声を削除するように会議のスケジュールを変更することを検討してください。既存の会議からダイヤルイン情報を会議して、既に予約されている会議でのオーディオの断片化を防止します。 

- 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、CsUserAcp コマンドレットを使用します。 詳細については、「 [CsUserAcp の削除](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)」を参照してください。 

- サードパーティの電話会議プロバイダーとの統合を無効にした後で、ユーザーの会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。 [「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。 

**概要:**

- 2021年7月31日以降にサードパーティ acp を引き続き使用することにした場合、サードパーティ acp は Skype for Business 会議への参加には使用できず、新しい会議にサードパーティ ACP のダイヤルイン情報が含まれないため、このような影響があります。 

- すべての影響を受けるユーザーのすべての会議について VoIP を無効にすることをお勧めします。これに2021より、VoIP 経由での参加者とサードパーティ ACP を介した参加者の間でオーディオが断片化されないようになります。 

    - 特定の開催者のすべての会議から VoIP を無効にするには、Set-csconferencingpolicy コマンドレットを使用して、ユーザーの会議ポリシーの AllowIPAudio パラメーターを false に設定します。 詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
 
- 組織がすべての会議で VoIP を無効にしていない場合は、Skype for Business Online とサードパーティ ACP との統合を無効にすることをお勧めします。また、サードパーティ ACP のダイヤルイン情報を削除するように会議をスケジュールし直すことをお勧めします。オーディオが断片化されないようにします。

    - 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、 [CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)コマンドレットを使用します。 

    - 会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。 [「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>パス #3: ダイヤルイン会議の使用を中止する

ダイヤルイン会議の使用を中止する組織 (Microsoft とサードパーティ ACP によって提供されることはありません) は、Skype for Business 会議のオーディオ部分をサポートするために、VoIP を最大限に活用することができます。 

このような組織では、ユーザーがサードパーティの電話会議プロバイダーを使用して、会議移行サービスを使用して会議を自動的に再スケジュールして、ダイヤルイン会議の情報を削除しないようにする必要があります。 

- 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、CsUserAcp コマンドレットを使用します。 詳細については、「 [CsUserAcp の削除](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)」を参照してください。 

- サードパーティの電話会議プロバイダーとの統合を無効にした後で、ユーザーの会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。 [「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。 

**概要:** 

- 2021年7月31日より前に、電話会議の使用を停止することを決定した組織には影響はありません。

- 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、CsUserAcp コマンドレットを使用します。 詳細については、「 [CsUserAcp の削除](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)」を参照してください。 

- サードパーティの電話会議プロバイダーとの統合を無効にした後で、ユーザーの会議を自動的に再スケジュールするには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。 [「会議移行サービス (MMS) の](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)セットアップ」をご利用ください。
