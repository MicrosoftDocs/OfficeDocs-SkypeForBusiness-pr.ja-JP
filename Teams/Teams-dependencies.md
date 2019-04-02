---
title: Microsoft Teams でのゲスト アクセスを承認する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 04/01/19
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87b0e6bf1f920ea4eaab4a4ed2bfb3f314b60601
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026065"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを承認する
===========================================

組織の要件を満たすために、Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。 すべての承認レベルが Office 365 テナントに適用されます。 それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。

- **Azure Active Directory**: Microsoft Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。 ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。 
- **Microsoft Teams**: Microsoft Teams のみを制御します。 
- **Office 365 グループ**: Office 365 グループおよび Microsoft Teams でのゲスト エクスペリエンスを制御します。
- **SharePoint Online と OneDrive for Business**: SharePoint Online、OneDrive for Business、Office 365 グループ、および Microsoft Teams でのゲスト エクスペリエンスを制御します。

これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。 など、マイクロソフトのチームにゲスト ユーザーを許可するが、組織の全体的なことができるようにするのにする場合は、だけにマイクロソフトのチームでのゲスト アクセスを無効します。 別の例: AAD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にすることができます。 SharePoint Online と OneDrive for Business には、Office 365 グループに依存しない独自のゲスト アクセス設定があります。 

> [!NOTE]
> ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。 

次の図では、Azure Active Directory、Microsoft Teams、および Office 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。

![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

次の図を示しています、高レベルは、一般的なゲスト アクセスへの招待と償還の流れを使用して、アクセス許可モデルに対するユーザーの操作性がどのように機能するか。

![招待と償還のフローの図](media/authorize-guest-image1.png)

アプリケーション、コンポーネント、およびコネクタ可能性があります独自のアクセス許可のセットを必要とするまたはある特定のユーザー アカウントに同意するものと、ここで注意する必要があります。 これらは、個別に付与する必要があります。 同様に、SharePoint では、余分な外部共有の境界を特定のユーザーのグループ、ユーザー、またはサイト レベルであってもを課す可能性があります。

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory 内のゲスト アクセスの制御

Azure AD を使用すると、来園者とはどのような方法で、社外の関係者をテナントに招待できるかどうかを判断します。 Azure の B2B のゲスト アクセスの詳細については、 [Azure Active Directory の B2B のゲスト ユーザーのアクセス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b)を参照してください。 Azure AD のロールの詳細については[、Azure Active Directory テナント内のパートナーの組織からユーザーにアクセス許可を付与](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role)を参照してください。

招待の設定は、テナント レベルで適用され、ディレクトリ、テナント、アプリケーション レベルでゲストのエクスペリエンスを制御します。 

![Azure Active Directory ポータルのユーザー設定のスクリーンショット。](media/teams_dependencies_image2.png)

Azure AD には、外部のユーザーを構成するのには次の設定が含まれています。

- **ゲスト ユーザーのアクセス許可が制限されます**: **[はい]** [来園者がディレクトリの特定のタスクのアクセス許可を持つ、ユーザー、グループ、またはその他のディレクトリ リソースを次のように列挙されていないことを意味します。 さらに、来園者は、ディレクトリ内の管理役割に割り当てることができません。 来園者は**** ことを意味では、通常のユーザーのディレクトリにあるディレクトリ データへのアクセスがありません。
- **管理者グループおよびゲストの招待者のロールにユーザーを招待できます**:**はい**できることを意味管理者グループおよびユーザーを「ゲスト招待者」の役割テナントには、来園者を招待します。 **なし**には、管理者ことを意味し、ユーザーは、テナントには、来園者を招待できません。
- **メンバーが招待することができます**:**はい**ディレクトリの管理者以外のメンバーが、Azure AD、SharePoint サイトまたは Azure のリソースなど、セキュリティで保護されたリソースに対する共同作業を行うには、来園者を招待することを意味します。 ディレクトリに来園者は管理者のみが招待することができます**しない**ことを意味します。</br>
      
    > [!NOTE]
    > 現時点では、チームでは、ゲストの招待者の役割をサポートしていません。 最低限の**メンバーを招待できます**] に **[はい]** のゲスト アクセスのチームで作業するのには表示/非表示を設定しなければなりません。
- **来園者が招待することができます**: **[はい]** をディレクトリ内には、来園者自身に招待できます、Azure AD、SharePoint サイトまたは Azure のリソースなど、セキュリティで保護されたリソースに対する共同作業を行うには、他のゲストを意味します。 来園者は**ない**ことを意味は、組織との共同作業には、他のゲストを招待できません。
 
来園者を招待することができますを制御する方法の詳細については、 [Azure Active Directory の B2B の共同作業のための代理人の招待状](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)を参照してください。

> [!NOTE]
> ゲストとして、テナントにどのドメインを招待することができますを管理することもできます。 [Office 365 のグループへのゲスト アクセスの許可/禁止](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)を参照してください。 

アカウント追加されるので、ディレクトリに自動的にチームにゲストを追加すると、Azure AD B2B にユーザー アカウントを手動で追加する必要はありません。 

Azure AD のライセンスを使用すると、1 ライセンスあたり 5 つまでの来園者を追加します。 Azure AD のライセンスの詳細については、 [Azure Active Directory B2B コラボレーションのライセンス ガイド](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)を参照してください。

## <a name="control-guest-access-in-teams"></a>チームでのゲスト アクセスの制御

チームでは、ゲストの経験が有効か無効か、組織を制御できます。 設定は、既定で無効にし、チームのだけテナントのレベルで適用します。

マイクロソフトのチームの管理センターからは、チームのゲスト アクセスの設定を管理できます。 詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。 


## <a name="control-guest-access-in-office-365-groups"></a>Office 365 のグループでのゲスト アクセスの制御

Office 365 グループから、自分の組織内のすべての Office 365 グループおよび Microsoft Teams へのゲスト ユーザーおよびゲスト アクセスの追加を制御できます。

1. Office 365 のグローバル管理者アカウントを使用してサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。
    
2. ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。
    
3. [**Office 365 グループ**] を選択します。
    
     ![Office 365 グループ](media/authorize-guest-image2.png)
  
4. Office 365 のグループ] ページでを**オン**または**オフ**、組織の Office 365 のアクセス グループの外のチームとグループの所有者を許可するかどうかに応じて、表示/非表示を設定します。 [**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。 **** するには、この切り替えを有効にする場合にマイクロソフト チームのグループを許可してチームの所有者は、Office 365 のグループに、組織外のユーザーを追加するかどうかは、コントロールに別のオプションが表示されます。 グループを許可して、チームの所有者は、ゲスト ユーザーを追加する場合は、**上**にこの切り替えを設定します。 
 
   ![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/authorize-guest-image3.png)

これらの設定では、テナントのレベルで適用され、Office 365 のグループとマイクロソフトのチームでのゲストの経験を制御します。

ゲスト アクセスのしくみ、ゲスト アクセス、およびよく寄せられる質問への回答を管理する方法を含め、グループでのゲスト アクセスの詳細については、 [Office 365 のグループにアクセスするゲスト](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)を参照してください。

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>ビジネスの SharePoint Online と OneDrive に、ゲスト アクセスを制御

Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。  
   
Teams のゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。

- SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**
    
    詳しくは、「[SharePoint Online 環境の外部共有を管理する](https://docs.microsoft.com/sharepoint/external-sharing-overview)」をご覧ください。
    
- Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**
    
    詳細については、上記の[Office 365 のグループでのゲスト アクセスの制御](#control-guest-access-in-office-365-groups)を参照してください。
  
これらの設定では、テナントのレベルで適用され、ビジネス、Office 365 のグループ、およびチームの SharePoint のオンライン、OneDrive でゲストの経験を制御します。

Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。 詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。

## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]