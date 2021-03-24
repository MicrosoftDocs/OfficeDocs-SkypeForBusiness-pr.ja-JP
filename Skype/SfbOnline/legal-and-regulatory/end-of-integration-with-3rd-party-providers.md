---
title: 'Skype for Business とサードパーティの電話会議プロバイダーを統合するサポート終了プログラム '
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
description: 2021 年 7 月 31 日に、サードパーティの電話会議プロバイダー (サード パーティ ACP) との Skype for Business の統合に向け、サポート終了プログラムが終了します。
ms.openlocfilehash: 5e48c7deb114136e0b12c2636cf562213890656d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100773"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Skype for Business とサードパーティの電話会議プロバイダーを統合するサポート終了プログラム 

Microsoft は、Skype for Business とサードパーティの電話会議プロバイダー (ACP) を統合するサポート終了プログラムの開始を発表しました。 

サポート終了プログラムは、2021 年 7 月 31 日に終了します。 プログラムが終了すると、Skype for Business とサードパーティの電話会議プロバイダーとの統合が停止し、その日付 (2021 年 7 月 31 日) に次の変更が行えます。

- サードパーティの ACP サービスから提供されたダイヤルイン番号を使用して Skype for Business 会議に参加しようとする参加者は、Skype for Business 会議に接続されなくなりました。
 
- サードパーティ ACP サービスが有効になっているユーザーは、新しい Skype for Business 会議の招待にダイヤルイン情報が自動的に含まれません。

サポート終了プログラムの開始のお知らせの一環として、次の変更が有効であり、サポート終了プログラムの終了まで引き続き適用されます。 

- サードパーティ ACP サービスを使用するように Skype for Business ユーザーが構成されていないお客様は、サードパーティ ACP サービスを使用するようにユーザーを構成することはできません。

- サードパーティの ACP サービスを使用するように構成された Skype for Business ユーザーを持つ既存のお客様は、サポート終了期間中、引き続き新しいユーザーを追加できます。 2021 年 7 月 31 日に適用される変更も適用されるので、サードパーティの ACP サービスを使用する追加の Skype for Business ユーザーを設定することをお勧めしません。

## <a name="preparing-for-this-change"></a>この変更の準備

この変更を準備するために、影響を受ける組織には、2021 年 7 月 31 日より前に、この予定されている更新プログラムについて、有効なユーザーに通知する必要があります。 

2021 年 7 月 31 日より後、ユーザーはオンライン会議に中断することなく Skype for Business を引き続き使用できます。ただし、Skype for Business または Microsoft Teams でのダイヤルイン電話会議が必要な場合、組織はユーザーが Microsoft が提供する電話会議を有効にする必要があります。 Microsoft 電話会議の詳細については、「電話会議 [」を参照してください](https://products.office.com/skype-for-business/audio-conferencing)。 

組織の目的の終了状態に応じて、次の 3 つのパスを実行できます。

- Microsoft 電話会議に移行します。 
- 引き続きサードパーティの電話会議プロバイダーを個別に使用します。 
- ダイヤルイン会議の使用を完全に停止します。

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>パス#1: Microsoft 電話会議への移行   

2021 年 7 月 31 日より前に Microsoft 電話会議に移行して移行を完了した組織は、その日以降にサービスへの影響を受け取る予定はありません。 Microsoft 電話会議に移行すると、組織に次の変更が加わります。 

- このサービスは、他のすべての Microsoft 365 または 365 Office請求されます。 

- 標準サブスクリプションを購入した場合、有料ダイヤルインの料金はユーザーごとの月次サブスクリプション の料金に含まれます。 

- 新しいダイヤルイン電話番号のセットが、各組織とそのユーザーに提供されます。 Microsoft 電話会議サービスの地理的な範囲を確認するには、「電話会議と通話プランの国と地域の可用性 [」を参照してください](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。
 
- サードパーティ ACP で有効になっているユーザーによって既にスケジュールされている会議は、Microsoft 電話会議のダイヤルイン情報を含む、自動的に再スケジュールされます。
 
- 各会議の会議 ID は動的です。つまり、各会議には専用の会議 ID が割り当てされます。 動的会議の ID は、セキュリティを強化し、会議のバック to バックのエクスペリエンスを向上します。

- このサービスのすべての使用には、電話会議サービスの使用条件が適用されます。 

Microsoft 電話会議への移行は簡単で、サービスのライセンスを取得した後、ほんの数ステップで行います。 Microsoft 電話会議に移行する方法については、次を参照してください。

- [Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**概要:**

- Microsoft 電話会議に移行し、2021 年 7 月 31 日より前に移行を完了した組織は、その日付以降にサービスに影響はありません。

- Microsoft 電話会議への移行の詳細については [、「Microsoft 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)または Office 365 で電話会議を試用または購入する」を参照してください。 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>パス#2: サードパーティーの電話会議プロバイダーを引き続き個別に使用する

2021 年 7 月 31 日以降にサードパーティ ACP を引き続き使用する組織では、サードパーティの ACP ダイヤルイン情報を使用して Skype for Business 会議の音声部分に参加できなくなったため、サービスへの影響が発生します。 

一部の参加者が VoIP を介して参加し、他の参加者にサードパーティ ACP 経由で参加することで、Skype for Business 会議の音声の断片化を防ぐために、これらの組織はユーザーの会議で VoIP の使用を無効に推奨します。 この方法では、すべての参加者がサードパーティ ACP を使用して会議の音声部分に参加する必要があります。また、会議の他のすべての作業負荷 (チャットや画面共有など) は、Skype for Business を通じて引き続きサポートされます。 

- 特定の開催者のすべての会議から VoIP を無効にするには、会議ポリシーの AllowIPAudio パラメーターを Set-CsConferencingPolicy コマンドレットを使用して false に設定します。 詳細については [、Set-CsConferencingPolicy を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
 
スケジュールに関して、また 2021 年 7 月 31 日の現在、サードパーティ ACP のダイヤルイン情報は Skype for Business 会議の招待に自動的に含まれません。 引き続きこの情報を会議の一部として含めたい場合、ユーザーは Skype for Business 会議の招待にダイヤルイン情報を手動で追加する必要があります。 

2021 年 7 月 31 日に、サードパーティの ACP ダイヤルイン情報を削除するために、ユーザーの既存の会議のスケジュールが自動的に変更されません。 ユーザーの会議で VoIP を有効にし続ける組織は、サードパーティ ACP の統合をユーザーに対して無効にし、会議移行サービスを使用して会議のスケジュールを変更して、サードパーティ電話会議のダイヤルイン情報を既存の会議から削除し、既にスケジュールされている会議での音声の断片化を防ぐ必要があります。 

- 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、Remove-CsUserAcpします。 詳細については [、Remove-CsUserAcp を参照してください](/powershell/module/skype/remove-csuseracp?view=skype-ps)。 

- サードパーティの電話会議プロバイダーとの統合を無効にした後、ユーザーの会議のスケジュールを自動的に変更するには、「ユーザーに対して会議移行を手動で実行する方法を確認する方法」を参照してください。 」 [の「Meeting Migration Service (MMS) のセットアップ」を参照してください](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。 

**概要:**

- サードパーティの ACP を 2021 年 7 月 31 日以降も引き続き使用する組織は、サードパーティの ACP を Skype for Business 会議に参加できません。また、新しい会議にはサードパーティの ACP ダイヤルイン情報が含まれるため、影響を受ける可能性があります。 

- 2021 年 7 月 31 日より前に、影響を受けるすべてのユーザーのすべての会議で VoIP を無効にし、VoIP 経由およびサードパーティ ACP 経由で参加する参加者間で音声が断片化されるのを防ぐことをお勧めします。 

    - 特定の開催者のすべての会議から VoIP を無効にするには、ユーザーの会議ポリシーの AllowIPAudio パラメーターを Set-CsConferencingPolicy コマンドレットを使用して false に設定します。 詳細については [、Set-CsConferencingPolicy を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
 
- 組織がすべての会議で VoIP を無効にしない場合は、ユーザーが Skype for Business Online とサードパーティ ACP との統合を使用し、会議を再スケジュールしてサードパーティ ACP ダイヤルイン情報を削除して音声の断片化を防ぐことをお勧めします。

    - 特定の開催者に対してサードパーティ電話会議の統合を無効にするには [、Remove-CsUserAcp コマンドレットを使用](/powershell/module/skype/remove-csuseracp?view=skype-ps) します。 

    - 会議のスケジュールを自動的に変更するには、「ユーザーに対して手動で会議移行を実行する方法」を参照してください。 」 [の「Meeting Migration Service (MMS) のセットアップ」を参照してください](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>パス#3: ダイヤルイン会議の使用を完全に停止する

ダイヤルイン会議の使用を完全に停止する組織 (Microsoft もサードパーティ ACP も提供しない) は、Skype for Business 会議の音声部分をサポートするために VoIP に完全に依存できます。 

これらの組織では、サードパーティの電話会議プロバイダーを使用してユーザーを無効にし、会議移行サービスを使用して会議のスケジュールを自動的に変更してダイヤルイン会議情報を削除する必要があります。 

- 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、Remove-CsUserAcpします。 詳細については [、Remove-CsUserAcp を参照してください](/powershell/module/skype/remove-csuseracp?view=skype-ps)。 

- サードパーティの電話会議プロバイダーとの統合を無効にした後、ユーザーの会議のスケジュールを自動的に変更するには、「ユーザーに対して会議移行を手動で実行する方法を確認する方法」を参照してください。 」 [の「Meeting Migration Service (MMS) のセットアップ」を参照してください](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。 

**概要:** 

- 2021 年 7 月 31 日以前に電話会議の使用を完全に停止する組織には影響はありません。

- 特定の開催者に対してサードパーティの電話会議の統合を無効にするには、Remove-CsUserAcpします。 詳細については [、Remove-CsUserAcp を参照してください](/powershell/module/skype/remove-csuseracp?view=skype-ps)。 

- サードパーティの電話会議プロバイダーとの統合を無効にした後にユーザーの会議のスケジュールを自動的に変更するには、「ユーザーに対して手動で会議移行を実行する方法を確認する方法」を参照してください。 」 [の「Meeting Migration Service (MMS) のセットアップ」を参照してください](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。