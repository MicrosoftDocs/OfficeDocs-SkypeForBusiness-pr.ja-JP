---
title: Skype for Business Server でのダイヤルイン会議の管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: '概要: Skype for Business Server でダイヤルイン会議を管理する方法について説明します。'
ms.openlocfilehash: 6bf5f13075b54d904ae70bc1b2106253442135db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119486"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でのダイヤルイン会議の管理
 
**概要:** Skype for Business Server でダイヤルイン会議を管理する方法について説明します。
  
このトピックでは、ダイヤルイン会議を管理する方法について説明します。 展開時にダイヤルイン会議を計画および構成する方法の詳細については [、「Plan for dial-in conferencing in Skype for Business Server」および「Configure](../../plan-your-deployment/conferencing/dial-in-conferencing.md) [dial-in conferencing in Skype for Business Server」](../../deploy/deploy-conferencing/dial-in-conferencing.md)を参照してください。
  
次のタスクを実行して、ダイヤルイン会議を有効または無効にする、アクセス番号を管理する、ダイヤルイン会議の PIN ポリシーを管理する、会議参加とアナウンスを残すを管理する、DTMF コマンドのキー マッピングを変更する、ダイヤルイン会議にユーザーを歓迎する。 
  
ダイヤル プランの管理の詳細については、「Create or modify a dial plan [in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
PSTN 使用法の詳細については、「Skype for Business で音声ポリシー、PSTN 使用法レコード、および音声ルートを [構成する」を参照してください](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してダイヤルイン会議を管理する

ダイヤルイン会議に関する情報を管理するには、次の方法を使用します。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで **[会議]** をクリックします。
    
ダイヤル プランと PSTN 使用法に関する情報を管理するには、次の方法を使用します。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[音声ルーティング] **をクリックします**。
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してダイヤルイン会議を管理する

Skype for Business Server 管理シェルを使用してダイヤルイン会議を管理するには、次のコマンドレットを使用します。
  
**ダイヤルイン構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |組織で使用するように構成された会議ディレクトリに関する情報を返します。 会議ディレクトリは、ダイヤルイン会議ユーザーが会議情報を検索するのに役立ちます。  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかに関する情報を取得します。  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |組織で使用するように構成されたすべてのダイヤルイン会議アクセス番号に関する情報を戻します。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用されるデュアルトーン多周波数 (DTMF) シグナリング設定を返します。 DTMF を使用すると、会議にダイヤルインするユーザーは、電話のキーパッドで会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Skype for Business Server ダイヤルイン会議で使用するためにサポートされている、地域/少数民族の言語を含む言語の一覧を返します。 これらの言語は、電話を使用して会議に出席しているユーザーにオーディオ メッセージと指示を中継するときに使用されます。  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |組織で使用されるダイヤル プランに関する情報を戻します。  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |ダイヤル プランを、1 つまたは複数のユーザーあるいはグループに割り当てます。  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |会議ディレクトリを、Microsoft Office Server 2007 R2 から Skype for Business Server にインポートします。 これにより、Skype for Business Server とコミュニケーション サーバー 2007 R2 Office相互運用性が提供されます。  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |既存の会議ディレクトリを別のプールに移動します。  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |組織で使用できるように新しい会議ディレクトリを作成します。  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |新しいダイヤルイン会議アクセス番号を作成します。  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |ダイヤルイン会議の構成設定の新しいコレクションを作成します。 これらの設定では、ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかが決定されます。 特に、参加者が会議の参加時に名前を記録する必要があるかどうか、およびユーザーの通話参加時や通話終了時のシステムからの通知方法 (または、通知するかどうか) に関する情報を戻します。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |ダイヤルイン会議に使用されるデュアルトーンマルチ周波数 (DTMF) シグナリング設定の新しいコレクションを作成します。  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |新しいダイヤル プランを作成します。  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |既存の会議ディレクトリを削除します。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議のアクセス番号を削除します。  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |1 つまたは複数のダイヤルイン会議の構成設定のコレクションを削除します。 これらの設定では、ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかが決定されます。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用されるデュアルトーン多周波数 (DTMF) シグナリング設定の既存のコレクションを削除します。  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号のプロパティ値を変更します。  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または退出するときに Skype for Business Server が応答する方法を決定する設定を変更します。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定を変更します。  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |既存のダイヤル プランを変更します。  <br/> |
   
**PIN ポリシー設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |組織での使用に構成されている、クライアントの暗証番号 (PIN) のポリシーに関する情報を戻します。 PIN 認証を使用すると、ユーザー名とパスワードの代わりに PIN を指定して、Skype for Business Server にアクセスできます。  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |クライアントの暗証番号 (PIN) ポリシーをユーザーまたはユーザーのグループに割り当てます。  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |新しいクライアント暗証番号 (PIN) ポリシーを作成します。  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |指定された暗証番号 (PIN) ポリシーを削除します。  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |1 つ以上の既存のクライアント個人識別番号 (PIN) ポリシーを変更します。  <br/> |
