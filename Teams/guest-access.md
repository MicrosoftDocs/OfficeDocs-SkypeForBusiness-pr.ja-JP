---
title: "Microsoft Teams でのゲスト アクセスを管理する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: f440e1d67166931365a24cb18e855a179fc532ef
ms.sourcegitcommit: 34abc255257716ab135e8eda7b07f8abb55a6bc7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2017
---
<a name="manage-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを管理する
======================================


Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。 ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。 たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。
  
    
    

Teams では、企業データを完全に制御して保持しながら、チーム、ドキュメント、リソース、チャット、アプリケーションへの外部アクセスをパートナーに提供できます。

Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。 Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。 Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。
  
    
    

## <a name="how-a-guest-joins-a-team"></a>ゲストがチームに参加する方法


  
    
    
Teams でのチーム所有者は、Web またはデスクトップを介してチームにゲストを追加することや、チームのゲストを管理することができます。 Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。
  
    
    

> [!NOTE]
> ゲストがチームに参加するには、管理者が Teams でゲスト アクセスを事前に有効にする必要があります。 この操作を行うには、Office 365 グローバル管理アカウントで[サインイン](https://portal.office.com/adminportal/home)します。 次に、[**設定**]  >  [**Services &amp; add-ins (サービスとアドイン)**]  >  [**Microsoft Teams**] の順に選択します。 [**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択し、[**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] で [**オン**] を選択します。 設定が有効になるまで最長で 1 時間かかる場合があります。 詳しくは、この記事の管理タブにある「Microsoft Teams のゲスト アクセスをオンまたはオフにする」をご覧ください。 
  
    
    

ゲストをチームのメンバーにする方法を次に示します。
  
    
    

- **手順 1** チーム所有者または Office 365 管理者は[チームにゲストを追加します](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)。
    
  
- **手順 2** Office 365 管理者またはチーム所有者は必要に応じてゲストが利用できる操作を管理します。 たとえば、チャネルの追加または削除、ファイルへのアクセスの無効化といった操作をゲストに許可します。
    
  
- **手順 3** ゲストは、チームへの参加を招待する「ようこそ」メールをチーム所有者から受け取ります。 招待状を受け取った後、ゲストは[チームやチャネルへの参加](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels)、メッセージの受信や返答、[チャネル内のファイルへのアクセス](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加を行うことができるようになります。 Teams の使用時には、すべてのユーザーがテキストとアイコンの組み合わせにより、チームにゲストが参加していることを知ることができます。 詳しくは、「[ゲストのエクスペリエンス](#guestexp)」をご覧ください。
    
  
ゲストは Teams の Web やデスクトップ クライアントを使っていつでもチームから脱退することができます。 詳しくは、「[How do I leave a team? (チームから脱退する方法を教えてください。)](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)」をご覧ください。
  
    
    

> [!NOTE]
> パートナーやコンサルタントなど組織外の人のみをゲストとして追加できます。 組織内のユーザーは通常のチーム メンバーとして参加できます。 
  
    
    

<a name="guestexp"></a>
## <a name="what-the-guest-experience-is-like"></a>ゲストのエクスペリエンスについて

ゲストは、チームへの参加を招待されると、チームに関する情報とメンバーとして利用できる内容を記載する「ようこそ」メール メッセージを受け取ります。 ゲストは、メール メッセージの招待状と引き換えに、チームやそのチャネルにアクセスできるようになります。
  
    
    

  
    
    
![Microsoft Teams のチーム所有者によってゲスト ユーザーに送信された「ようこそ」メール メッセージの例をスクリーンショットに示します。 メッセージには、チーム所有者によってカスタマイズ可能なテキスト、さらにチャット、通話、会議など Teams の機能に関する簡潔な説明が記載されます。](media/bc0deb82-6394-4280-8fed-312645c8fefe.png)
  
    
    
すべてのチーム メンバーは、チーム所有者がゲストを追加した旨およびそのゲストの名前を知らせるメッセージを確認することができます。 チームのメンバー全員がゲストが誰であるかを簡単に判断できます。 次のサンプル チームのスクリーンショットで示すように、バナーに「This team has guests (チームにゲストが参加しました)」と示され、各ゲストの名前の横に「ゲスト」ラベルが表示されます。
  
    
    

  
    
    
![スクリーンショットは Northwind Traders の Marketing チャネルの一部を示しています。上部のバナーに「This team has guests (チームにゲストが参加しています)」と示され、ゲストのユーザーはその名前の横の「ゲスト」によって識別されます。](media/33394a31-7d10-4950-8b39-b7d9953397c3.png)
  
    
    
次の表に、組織のチーム メンバーが利用できる Microsoft Teams の機能とチームのゲスト ユーザーが利用できる機能との比較を示します。
  
    
    


|**Teams の機能**|**組織の Teams ユーザー**|**ゲスト ユーザー**|
|:-----|:-----|:-----|
|チャネルの作成  <br/>  *この機能はチーム所有者によって制御されます。*  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|プライベート チャットに参加する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|チャネルの会話に参加する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|メッセージを投稿、削除、編集する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|チャネル ファイルを共有する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|チャット ファイルを共有する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|アプリ (タブ、ボット、コネクタ) を追加する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|テナント全体およびチーム/チャネルのゲスト アクセス ポリシーを作成する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|Office 365 テナントのドメイン外のユーザーを招待する  <br/> ||![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|チームを作成する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|パブリック チームを検出して参加する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|組織図を表示する  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
   

    
> [!NOTE]
> ゲストが利用できる機能は Office 365 の管理者によって制御されます。 
  
    
## <a name="manage-guests"></a>ゲストを管理する


ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。 追加の Office 365 ライセンスは不要です。
  
    
    
Teams のゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。 管理者は Office 365 管理センターでゲスト アクセスを管理できます。 詳しくは、「[Microsoft Teams へのゲスト アクセスを管理する](#manageguest)」と「[Control guest access to Microsoft Teams (Microsoft Teams へのゲスト アクセスを制御する)](#controlguest)」をご覧ください。
  
    
    

> [!NOTE]
> Teams のゲスト アクセスのテナント設定は、ゲストのサインインのみを拒否します。 チーム所有者は、所有するチームに新しいゲストを招待したり、既存のディレクトリ ゲスト ユーザーを追加できます。 Teams は、テナントへのゲスト ユーザーの追加の許可または拒否において、常に Azure Active Directory の外部設定を優先します。 
  
    
    

さらに、Azure Active Directory ポータルを使用して、ゲストの管理、Office 365 や Teams のリソースへのゲスト アクセスの管理を行うことができます。 Teams のゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。 Azure Active Directory B2B について詳しくは、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。
  
    
    

#### <a name="related-key-services-and-dependencies"></a>関連する主要なサービスと依存関係

Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。 さらに、Teams は、Office 365 グループを利用して、チームのメンバーシップやチームのデータ分類設定などのその他のプロパティを保管します。
  
    
    
Teams のゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。
  
    
    

- SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**
    
    詳しくは、「[SharePoint Online 環境の外部共有を管理する](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)」をご覧ください。
    
  
- Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**
    
    詳しくは、「[Control guest access to Microsoft Teams (Microsoft Teams へのゲスト アクセスを制御する)](#controlguest)」をご覧ください。
    
  

#### <a name="turn-on-or-off-guest-access-for-microsoft-teams"></a>Microsoft Teams のゲスト アクセスをオンまたはオフにする
<a name="bkmk_TurnonOrTurnOff"> </a>


1. Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。
    
  
2. ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。
    
     ![Office 365 にサインインし、Office 365 管理センターに移動して、[設定]、[Services &amp; add-ins (サービスとアドイン)] の順に選択します。](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. [**Microsoft Teams**] を選択します。
    
     ![次のスクリーンショットは、Office 365 管理センターで選択した Microsoft Teams アドインのオプションを示しています。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. [**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択します。
    
  
![Microsoft Teams アドインのスクリーンショットでは、ゲスト ライセンスが選択され、Microsoft Teams オプションがオンに設定されています。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
  
  
5. [**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] の横にあるトグルをクリックまたはタップして [**オン**] にして組織の Teams とゲスト アクセスをオンにし、[**保存**] を選択します。 
    
  
> [!NOTE]
> 設定が有効になるまで最長で 1 時間かかる場合があります。 
  
    
## <a name="control-adding-guest-users-to-microsoft-teams-and-office-365-groups"></a>Microsoft Teams や Office 365 グループへのゲスト ユーザーの追加を制御する
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。
    
  
2. ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。
    
  
3. [**Office 365 グループ**] を選択します。
    
     ![Office 365 グループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. 組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するかどうかに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。 [**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。
    
    
  
    
    
![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
  
  
  
<a name="controlguest"> </a>
## <a name="turn-on-or-off-the-sharing-option-for-office-365"></a>Office 365 の [共有] オプションをオンまたはオフにする


[共有] オプションでは、組織へのゲストの追加を許可します。 既定では、[共有] オプションは有効です。 [共有] オプションをオフにする方法について詳しくは、「[[共有] オプションをオンまたはオフにする](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)」をご覧ください。
  
    
    

> [!IMPORTANT]
> [共有] オプションをオフにすると、ゲスト アクセスが利用できなくなります。 
  

## <a name="use-powershell-to-control-guest-access"></a>PowerShell を使用してゲスト アクセスを制御する
<a name="bkmk_UsePowerShell"> </a>

Office 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。 PowerShell を使用すると、次の操作を行うことができます。
  
    
    

- すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する
    
  
- すべてのチームおよび Office 365 グループへのゲストの追加を許可する
    
  
- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する
    
  
詳しくは、「[PowerShell を使用してゲスト アクセスを制御する](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)」をご覧ください。
  
    
    
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。 Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。 詳しくは、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。
  
    
    
<a name="manageguest"> </a>
### <a name="view-guest-users"></a>ゲスト ユーザーを表示する



1. Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。
    
  
2. [**ユーザー**]  >  [**ゲスト ユーザー**] に移動します。
    
    
  
    
    
![次のスクリーンショットは、Office 365 管理センターの [ユーザー] セクションで選択したゲスト ユーザー オプションを示しています。](media/95b83ff5-72ef-4668-b541-4e25b767620a.png)
  
    

## <a name="invite-guest-users"></a>ゲスト ユーザーを招待する
<a name="bkmk_UsePowerShell"> </a>

チーム所有者や Office 365 管理者は、個別に[ゲストをチームに招待する](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)ことができます。 ただし、管理者は Office 365 管理センターや Azure Active Directory ポータルを使用して一度の操作で複数のゲストを招待することはできません。 一元的にゲストを招待する場合に、Azure Active Directory B2B コラボレーション プレビューを使用することができます。 詳しくは、「[Azure AD B2B コラボレーション プレビューについて](https://go.microsoft.com/fwlink/p/?linkid=853011)」をご覧ください。
  
    
    

## <a name="edit-guest-user-information"></a>ゲスト ユーザー情報を編集する
<a name="bkmk_UsePowerShell"> </a>

現時点では、Office 365 管理センターや Exchange 管理センターからゲスト情報を編集することはできません。 ゲスト アカウントを編集するには (表示名やプロフィール写真など)、Azure Active Directory ポータルに移動します。 詳しくは、「[Office 365 ID と Azure Active Directory について](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)」をご覧ください。
  
    
    
## <a name="frequently-asked-questions-for-admins"></a>管理についてよく寄せられる質問
<a name="bkmk_UsePowerShell"> </a>

Microsoft Teams のチームへの参加にゲストを招待することについて、Office 365 管理者が持つ一般的な質問を以下に示します。
  
    
    

#### <a name="what-is-a-guest"></a>ゲストとは何ですか?


  
    
    
ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。 ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。
  
    
    

  
    
    

#### <a name="who-can-be-added-as-a-guest-user"></a>ゲスト ユーザーとして追加できるユーザーを教えてください。

Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。
  
    
    

#### <a name="can-users-add-people-within-my-organization-who-are-not-part-of-the-team-as-a-guest"></a>ユーザーはチームのメンバーでない組織内の人をゲストとして追加できますか?

パートナーやコンサルタントなど組織外の人のみをゲストとして追加できます。 ユーザーは、組織内の人を通常のチーム メンバーまたはサブスクライバーとして参加するように招待できます。
  
    
    

#### <a name="why-does-a-user-get-the-message-contact-your-administrator-when-they-try-to-add-a-guest-to-their-team"></a>ユーザーがチームにゲストを追加しようとすると「Contact your administrator (管理者にお問い合わせください)」というメッセージを受信するのはなぜですか?

Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。 ユーザーがこのメッセージを受信する場合は、ゲスト機能が有効になっていない可能性があります。
  
    
    

#### <a name="how-can-a-global-admin-add-a-new-guest-user-to-the-organization"></a>グローバル管理者が組織に新しいゲスト ユーザーを追加する方法を教えてください。

グローバル管理者は複数の方法で新しいゲスト ユーザーを組織に追加できます。
  
    
    

- チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用して[チームにゲストを追加](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)できます。
    
  
- Azure Active Directory B2B コラボレーションを使用して組織にゲストを追加します。 Azure Active Directory B2B コラボレーションを使用すると、グローバル管理者は、2000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。 詳しくは、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?LinkId=826383)」をご覧ください
    
  

#### <a name="is-there-a-way-to-block-individual-guest-users"></a>個別にゲスト ユーザーを拒否する方法はありますか?

いいえ。個別にゲスト ユーザーを拒否することはできません。
  
    
    

#### <a name="can-global-admins-block-guests-in-teams-and-still-allow-guests-to-access-sharepoint-sites"></a>グローバル管理者はチームでのゲストを拒否する一方でゲストによる SharePoint サイトへのアクセスを許可することはできますか?

はい。グローバル管理者は、SharePoint の外部共有をオンに設定している場合に、Azure Active Directory Powershell コマンドレットを使用して Company オブジェクトの _AllowGuestAccessToGroups_ パラメータを無効にすることができます。
  
    
    

#### <a name="what-other-controls-are-available-to-it-admins-to-manage-guests-in-microsoft-teams"></a>IT 管理者が Microsoft Teams でのゲストを管理するために利用できるその他の制御操作を教えてください。

IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。 これらの制御は Office 365 管理センターを介して利用できます。 ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。
  
    
    

#### <a name="can-users-share-a-team-file-with-an-external-user-who-isnt-a-member-of-the-team"></a>ユーザーはチームのメンバーでない外部ユーザーとチーム ファイルを共有することができますか?

いいえ。 ユーザーは、チームへの参加を招待されたゲストとのみ Microsoft Teams ファイルを共有できます。
  
    
    

#### <a name="is-an-additional-office-365-license-required-for-guest-access"></a>ゲスト アクセスには追加の Office 365 ライセンスが必要ですか?

追加のライセンスは不要です。 ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。
  
    
    

#### <a name="do-office-365-and-azure-active-directory-service-limits-apply-to-guests"></a>Office 365 や Azure Active Directory サービスの制限はゲストに適用されますか?

はい。ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。
  
    
    

  
    
    

#### <a name="how-long-does-it-take-until-the-guest-user-settings-take-effect-in-the-office-365-organization"></a>ゲスト ユーザーの設定が Office 365 組織に反映されるまでどのくらいの時間がかかりますか?

ゲスト設定は Azure Active Directory で設定します。 その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。
  
    
    

#### <a name="can-a-global-admin-manage-sharepoint-online-external-user-settings-for-the-teams-connected-team-site"></a>グローバル管理者は Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できますか?

はい。Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。 詳しくは、「[SharePoint チーム サイト設定を管理する](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。
  
    
    

  
    
    

#### <a name="how-does-conditional-access-work-with-guest-access"></a>条件付きアクセスはゲスト アクセスに対してどのように作用しますか?

Azure Active Directory B2B コラボレーションでは、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。 このポリシーは、フルタイムの従業員や組織のメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベルまたは個々のユーザー レベルで適用できます。 こうしたポリシーはリソース組織で実施します。 詳しくは、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。
  
    
    

#### <a name="if-i-have-a-team-with-an-office-365-group-and-i-add-a-guest-to-the-group-does-that-user-automatically-get-access-to-the-team"></a>Office 365 グループとのチームを所有している場合に、そのグループにゲストを追加すると、ゲストはチームへのアクセスを自動的に取得しますか?

はい。そのユーザーはチームにアクセスできます。 Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。
  
    
    

#### <a name="what-event-appears-in-the-audit-log-to-indicate-a-guest-has-been-sent-an-invitation"></a>監査ログにおいて、ゲストに招待状が送信されたことを示すイベントを教えてください。

ゲストの追加は、Azure Active Directory または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。 Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。 詳しくは、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センターとコンプライアンス センターで監査ログを検索する](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。
  
    
    

#### <a name="if-i-have-existing-guest-users-that-were-added-via-azure-ad-b2b-office-365-groups-or-sharepoint-online-do-i-have-to-do-anything-else-with-them-for-microsoft-teams"></a>Azure AD B2B、Office 365 グループ、SharePoint Online を介して追加したゲスト ユーザーが存在する場合、そのユーザーのために Microsoft Teams でその他の操作を行う必要はありますか?

Azure Active Directory B2B、Office 365 グループまたは SharePoint Online を介してすでに追加しているゲスト ユーザーはすぐに利用できます。 Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。
  
    
    

#### <a name="if-external-accounts-are-available-does-that-mean-external-sharing-is-enabled"></a>外部アカウントを利用できるということは、外部共有が有効になっていることを意味しますか?

管理者は、外部共有の設定から独立して、Azure Active Directory でゲスト アカウントを作成することができます。 外部共有がオフの場合、管理者のみがゲスト アカウントを作成できます。
  
    
    

  
    
    

## <a name="more-information"></a>詳細情報

 [Microsoft Teams の管理者設定](https://support.office.com/en-us/article/Administrator-settings-for-Microsoft-Teams-3966a3f5-7e0f-4ea9-a402-41888f455ba2)
  
    
    
 [Microsoft Teams についてよく寄せられる質問 - 管理者向けヘルプ](https://support.office.com/en-us/article/Frequently-asked-questions-about-Microsoft-Teams-–-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)
  
    
    
 [チームへのゲストの追加](https://support.office.com/en-us/article/Adding-guests-to-teams-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)
  
    
    
ビデオ: [Deep Dive into Guest Access](https://go.microsoft.com/fwlink/p/?linkid=858791)
  
    
    

