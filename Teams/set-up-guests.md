---
title: "Microsoft Teams へのゲスト アクセスをセットアップする"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams でのゲスト アクセス機能を有効にします。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをセットアップする
======================================

Microsoft Teams は Office 365 グループに基づき構築されていて、SharePoint Online も利用しています。 このため、Teams でのゲスト アクセス機能をオンにすることに加えて、特定の設定を Office 365 グループおよび SharePoint Online で有効にする必要があります。


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>Office 365 グループでのゲストの追加を許可する
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。
    
  
2. ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。
    
  
3. [**Office 365 グループ**] を選択します。
    
     ![Office 365 グループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. 組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するかどうかに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。 [**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。


![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>SharePoint Online での共有を有効にする

SharePoint Online の [共有] オプションでは、組織へのゲストの追加を許可します。 既定では、[共有] オプションは有効です。 [共有] オプションをオフにする方法の詳細については、「[[共有] オプションをオンまたはオフにする](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)」をご覧ください。
  
   管理者は、外部共有の設定から独立して、Azure Active Directory でゲスト アカウントを作成することができます。 外部共有がオフの場合、管理者のみがゲスト アカウントを作成できます。 
    

> [!IMPORTANT]
> [共有] オプションをオフにすると、ゲスト アクセスが利用できなくなります。 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをオンまたはオフにする
<a name="bkmk_TurnonOrTurnOff"> </a>

Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。 

ゲスト設定は Azure Active Directory で設定します。 その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。 ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。



1. Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。
    
  
2. ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。
    
     ![Office 365 にサインインし、Office 365 管理センターに移動して、[設定]、[Services &amp; add-ins (サービスとアドイン)] の順に選択します。](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. [**Microsoft Teams**] を選択します。
    
     ![次のスクリーンショットは、Office 365 管理センターで選択した Microsoft Teams アドインのオプションを示しています。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. [**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択します。
   
    ![Microsoft Teams アドインのスクリーンショットでは、ゲスト ライセンスが選択され、Microsoft Teams オプションがオンに設定されています。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. [**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] の横にあるトグルをクリックまたはタップして [**オン**] にして組織の Teams とゲスト アクセスをオンにし、[**保存**] を選択します。 
    
  

