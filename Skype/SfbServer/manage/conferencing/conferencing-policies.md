---
title: Skype での会議のポリシーを管理するビジネス サーバー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '概要: ビジネス サーバーの Skype での会議ポリシーを管理する方法を説明します。'
ms.openlocfilehash: 1bfe046f4d46617880d1a6bff34391bbb0b8837c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919403"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Skype での会議のポリシーを管理するビジネス サーバー
 
**の概要:** ビジネス サーバーの Skype での会議ポリシーを管理する方法について説明します。
  
このトピックでは、電話会議ポリシーを管理する方法について説明します。 予定し、会議を展開する方法の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)と[ビジネス サーバーの Skype で会議を展開](../../deploy/deploy-conferencing/deploy-conferencing.md)を参照してください。
  
電話会議ポリシーにより、会議に IP オーディオと IP ビデオを組み込むことができるかどうかから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションを定義できます。電話会議ポリシーを使用すると、セキュリティ、帯域幅、および会議の法的側面を管理できます。
  
電話会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。 設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。 ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。 ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。 ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。
  
グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。 また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、会議のポリシーを管理します。

会議ポリシーを管理するには、Skype を使用してビジネス サーバーのコントロール パネルの。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して会議のポリシーを管理します。

Skype ビジネス サーバー管理シェルを使用して会議を管理するためには、次のコマンドレットを使用します。
  
**電話会議ポリシーの設定**

|**コマンドレット**|**説明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するために構成されている電話会議ポリシーに関する情報を戻します。  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |電話会議ポリシーをユーザーごとのスコープで割り当てます。  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |組織で使用するために新しい電話会議ポリシーを作成します。  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |指定の電話会議ポリシーを削除します。  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |既存の電話会議ポリシーを変更します。  <br/> |
   

