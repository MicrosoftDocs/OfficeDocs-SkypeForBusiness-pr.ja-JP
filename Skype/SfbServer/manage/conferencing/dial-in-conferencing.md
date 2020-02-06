---
title: Skype for Business Server でダイヤルイン会議を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: '概要: Skype for Business Server でダイヤルイン会議を管理する方法について説明します。'
ms.openlocfilehash: ba8b62456a1fa2024f2cf37642658e76d528ebf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818578"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議を管理する
 
**概要:** Skype for Business Server でダイヤルイン会議を管理する方法について説明します。
  
このトピックでは、ダイヤルイン会議を管理する方法について説明します。 展開時にダイヤルイン会議を計画して構成する方法の詳細については、「skype for [Business server でダイヤルイン会議を計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)する」および「 [Skype for business server でダイヤルイン会議を構成](../../deploy/deploy-conferencing/dial-in-conferencing.md)する」を参照してください。
  
ダイヤルイン会議を管理するには、ダイヤルイン会議を有効または無効にする方法、アクセス番号を管理する方法、ダイヤルイン会議の PIN ポリシーを管理する方法、電話会議への参加を管理する方法、およびお知らせを残す方法を管理するためのタスクを実行することができます。 DTMF のキーマッピングを変更します。コマンド、ダイヤルイン会議へようこそ。 
  
ダイヤルプランの管理について詳しくは、「 [Skype For Business Server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」をご覧ください。
  
PSTN の使用状況の詳細については、「 [Skype For business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)」を参照してください。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ダイヤルイン会議を管理する

ダイヤルイン会議に関する情報を管理するには:
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックします。
    
ダイヤル プランと PSTN 使用法に関する情報を管理するには:
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ダイヤルイン会議を管理する

Skype for Business Server 管理シェルを使ってダイヤルイン会議を管理するには、次のコマンドレットを使用します。
  
**ダイヤルイン会議の設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |組織用に構成された電話会議ディレクトリに関する情報を戻します。電話会議ディレクトリは、ダイヤルイン会議ユーザーが電話会議情報を検索するのに役立ちます。  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかに関する情報を取得します。  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |組織で使用するように構成されているすべてのダイヤルイン会議アクセス番号に関する情報を戻します。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議で使用されるデュアルトーン多重周波数 (DTMF) の信号設定を戻します。DTMF を使用すると、会議にダイヤルインするユーザーは、電話のキーパッドで会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Skype for Business Server のダイヤルイン会議での使用がサポートされている地域/少数言語を含む言語のリストを返します。 これらの言語は、電話を使用して電話会議に出席しているユーザーにオーディオ メッセージと指示を中継するときに使用されます。  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |組織で使用されるダイヤル プランに関する情報を戻します。  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |ダイヤル プランを、1 つまたは複数のユーザーあるいはグループに割り当てます。  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Microsoft Office Communications Server 2007 R2 から Skype for Business Server に会議ディレクトリをインポートします。 これにより、Skype for Business Server と Office Communications Server 2007 R2 の間の相互運用性が提供されます。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリをあるプールから別のプールに移動します。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |組織で使用する新しい電話会議ディレクトリを作成します。  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |新しいダイヤルイン会議アクセス番号を作成します。  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |ダイヤルイン会議の構成設定の新しいコレクションを作成します。 この設定では、ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかを決定します。 特に、参加者が電話会議の参加時に名前を記録する必要があるかどうか、およびユーザーの通話参加時や通話終了時のシステムからの通知方法 (または、通知するかどうか) に関する情報を戻します。  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の新しいコレクションを作成します。  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |新しいダイヤル プランを作成します。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |既存の電話会議ディレクトリを削除します。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号を削除します。  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |1 つまたは複数のダイヤルイン会議の構成設定のコレクションを削除します。 この設定では、ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかを決定します。  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定の既存のコレクションを削除します。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |既存のダイヤルイン会議アクセス番号のプロパティ値を変更します。  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |ユーザーがダイヤルイン会議に参加または脱退したときに Skype for Business Server がどのように応答するかを決定する設定を変更します。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |ダイヤルイン会議に使用するデュアルトーン多重周波数 (DTMF) シグナリング設定を変更します。  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |既存のダイヤル プランを変更します。  <br/> |
   
**PIN ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |組織での使用に構成されている、クライアント暗証番号 (PIN) ポリシーに関する情報を戻します。 PIN 認証を使用すると、ユーザーは、ユーザー名とパスワードの代わりに PIN を指定して、Skype for Business Server にアクセスできます。  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |クライアント暗証番号 (PIN) ポリシーをユーザーまたはユーザー グループに割り当てます。  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |新しいクライアント暗証番号 (PIN) ポリシーを作成します。  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |指定した暗証番号 (PIN) ポリシーを削除します。  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |1 つまたは複数の既存のクライアント暗証番号 (PIN) ポリシーを変更します。  <br/> |
   

