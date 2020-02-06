---
title: Skype for Business Server で会議の構成設定を管理する
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '概要: Skype for Business Server で会議の構成設定を管理する方法について説明します。'
ms.openlocfilehash: cefdf304d8cf5ed6ff4560dd5416283d733c3db2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818528"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議の構成設定を管理する
 
**概要:** Skype for Business Server で会議の構成設定を管理する方法について説明します。
  
このトピックでは、会議の構成設定を管理する方法について説明します。 会議の計画と展開の詳細については、「Skype for business [server で会議の計画を立てる](../../plan-your-deployment/conferencing/conferencing.md)」および「 [Skype for business server で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)する」を参照してください。
  
会議の構成設定では、ユーザーが作成できる会議の種類を指定でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについても) 制御できます。 これらの設定は、スケジュールされた会議にのみ影響します。Skype for Business の [今すぐ会議] オプションをクリックして作成されたアドホック会議には影響ありません。
  
会議の構成設定では、次の設定を定義します。
  
- 公衆交換電話網 (PSTN) からダイヤルインするユーザーをロビーに移動するかどうか
    
- 発表者の条件
    
- 会議の種類を既定で割り当てるかどうか
    
- 匿名 (認証されていない) ユーザーを既定で許可するかどうか
    
会議の特性は、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して定義できます。 
  
会議の設定は、グローバルレベル (既定で作成)、サイトレベル、またはプールレベルで指定できます。 既定では、グローバル設定が会議に関する操作性を定義します。 プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。 プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。 サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議の設定を管理する

Skype for Business Server コントロールパネルを使用して会議の設定を管理するには、次の操作を行います。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の設定を管理する

Skype for Business Server 管理シェルを使用して会議を管理するには、次のコマンドレットを使用します。
  
**会議の構成設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定に関する情報を戻します。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |サイト スコープまたはサービス スコープで会議の構成設定の新しいコレクションを作成します。  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |会議の構成設定の既存のコレクションを削除します。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |組織で現在使用されている会議の構成設定を変更します。  <br/> |
   

