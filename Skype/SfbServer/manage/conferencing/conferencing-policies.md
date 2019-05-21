---
title: Skype for Business Server の会議ポリシーを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '概要: Skype for Business Server で会議ポリシーを管理する方法について説明します。'
ms.openlocfilehash: d835c4760ef3e77bc36f21e64cb80aeb618526ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289056"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server の会議ポリシーを管理する
 
**概要:** Skype for Business Server で会議ポリシーを管理する方法について説明します。
  
このトピックでは、電話会議ポリシーを管理する方法について説明します。 会議の計画と展開の詳細については、「Skype for business [server で会議の計画を立てる](../../plan-your-deployment/conferencing/conferencing.md)」および「 [Skype for business server で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)する」を参照してください。
  
電話会議ポリシーにより、会議に IP オーディオと IP ビデオを組み込むことができるかどうかから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションを定義できます。電話会議ポリシーを使用すると、セキュリティ、帯域幅、および会議の法的側面を管理できます。
  
電話会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。 設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。 ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。 ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。 ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。
  
グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。 また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議のポリシーを管理する

Skype for Business Server コントロールパネルを使用して会議のポリシーを管理するには、次の操作を行います。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議のポリシーを管理する

Skype for Business Server 管理シェルを使用して会議を管理するには、次のコマンドレットを使用します。
  
**電話会議ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するために構成されている電話会議ポリシーに関する情報を戻します。  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |電話会議ポリシーをユーザーごとのスコープで割り当てます。  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するために新しい電話会議ポリシーを作成します。  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |指定の電話会議ポリシーを削除します。  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |既存の電話会議ポリシーを変更します。  <br/> |
   

