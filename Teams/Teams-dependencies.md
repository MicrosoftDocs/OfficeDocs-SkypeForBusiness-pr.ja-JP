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
ms.openlocfilehash: bcd6741f100ff7ad89127c4cc5f53008e9d3608a
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400547"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセスを承認する
===========================================

組織の要件を満たすために、Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。 すべての承認レベルが Office 365 テナントに適用されます。 それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。

- **Azure Active Directory**: Microsoft Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。 ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。 
- **Microsoft Teams**: Microsoft Teams のみを制御します。 
- **Office 365 グループ**: Office 365 グループおよび Microsoft Teams でのゲスト エクスペリエンスを制御します。
- **SharePoint Online と OneDrive for Business**: SharePoint Online、OneDrive for Business、Office 365 グループ、および Microsoft Teams でのゲスト エクスペリエンスを制御します。

これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。 たとえば、自分の Microsoft Teams でゲスト ユーザーを許可せず、組織全体では許可する場合、Microsoft Teams でゲスト アクセスをオフにするだけです。 別の例: AAD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にすることができます。 SharePoint Online と OneDrive for Business には、Office 365 グループに依存しない独自のゲスト アクセス設定があります。 

> [!NOTE]
> ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。 

次の図では、Azure Active Directory、Microsoft Teams、および Office 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。

![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

次の図は、一般的なゲスト アクセスの招待と引き換えフローを通じて、ユーザーの作業環境がアクセス許可モデルとどのように連動するかを大まかに示しています。

![招待と引き換えフローの図](media/authorize-guest-image1.png)

ここで重要なことは、アプリ、ボット、コネクタが独自のアクセス許可のセットや、ユーザー アカウントに固有の同意が必要な可能性があることです。 それぞれに付与する必要があります。 同様に SharePoint は、特定のユーザー、ユーザーのグループ、またはサイト レベルであっても、外部共有の境界を追加することがあります。

前の 2 つの図は、 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)の使用もできます。

## <a name="control-guest-access-in-azure-active-directory"></a>Azure Active Directory のゲスト アクセスを管理する

Azure AD を使用し、外部の共同作業者をゲストとして、どんな方法で、テナントに招待できるかどうかを決定します。 Azure B2B のゲスト アクセスの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b)」を参照してください。 Azure AD の役割に関する詳細については、「[Azure Active Directory テナントでパートナー組織からユーザーにアクセス許可を付与する](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role)」を参照してください。

招待の設定は、テナント レベルで適用され、ディレクトリ、テナント、アプリケーション レベルでゲストのエクスペリエンスを制御します。 Azure ポータルでこれらの設定を構成するには、 **Azure Active Directory**に移動 > **ユーザー** > **ユーザーの設定**、し、[**外部ユーザー**]**外部の共同作業の設定の管理**を選択します。

Azure AD には、外部ユーザーを構成する次の設定があります。

- [**Guest user permissions are limited (ゲスト ユーザーのアクセス権を制限)**]: [**Yes (はい)**] の場合、ゲストにはユーザー、グループ、その他のディレクトリ リソースの列挙などの特定のディレクトリのタスクに対するアクセス権はありません。 また、自分のディレクトリでの管理者の役割にゲストを割り当てることはできません。 [**No (いいえ)**] の場合、自分のディレクトリで一般ユーザーが持っているアクセス権と同じアクセス権を、ゲスト ユーザーが持つことになります。
- [**Admins and users in the guest inviter role can invite (管理者とゲスト招待元ロールのユーザーが招待可能)**]: [**Yes (はい)**] の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。 [**No (いいえ)**] の場合、管理者およびユーザーはゲストをテナントに招待できません。
- [**Members can invite (メンバーが招待可能)**]: [**Yes (はい)**] の場合、自分のディレクトリ内の管理者ではないメンバーが、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどで共同作業を行うゲストを招待することができます。 [**No (いいえ)**] の場合、ゲストを自分のディレクトリに招待できるのは管理者のみになります。</br>
      
    > [!NOTE]
    > 現時点では、Teams はゲストの招待者の役割をサポートしていません。 Teams でゲスト アクセスを機能させるには、少なくとも[**Members can invite (メンバーが招待可能)**] を [**Yes (はい)**]に設定する必要があります。
- [**Guests can invite (ゲストが招待可能)**]: [**Yes (はい)**] の場合、自分のディレクトリ内のゲストは独自に他のゲストを招待して、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどでそれらのゲストと共同作業を行うことができます。 [**No (いいえ)**] の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。
 
来園者を招待することができますを制御する方法の詳細については、 [Azure Active Directory の B2B の共同作業のための代理人の招待状](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)を参照してください。

> [!NOTE]
> どのドメインをゲストとしてテナントに招待できるかを管理することもできます。 詳細については、「[Office 365 グループへのゲスト アクセスを許可/拒否する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)」を参照してください。 

ユーザー ゲスト アカウントを手動で Azure AD B2B に追加する必要はありません。ゲストを Teams に追加すると、アカウントは自動的にディレクトリに追加されます。 

Azure AD ライセンスでは、1 つのライセンスにつき、最大 5 人のゲストを追加できます。 Azure AD のライセンスに関する詳細については、「[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)」を参照してください。

## <a name="control-guest-access-in-teams"></a>Teams でのゲスト アクセスを管理する

Teams では、自分の組織においてゲストのエクスペリエンスを有効にするか無効にするかを管理できます。 この設定は既定で無効になっており、Teams のテナント レベルのみで適用されます。

Microsoft Teams 管理センターで Teams のゲスト アクセスの設定を管理できます。 詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。 


## <a name="control-guest-access-in-office-365-groups"></a>Office 365 グループでゲスト アクセスを管理する

Office 365 グループから、自分の組織内のすべての Office 365 グループおよび Microsoft Teams へのゲスト ユーザーおよびゲスト アクセスの追加を制御できます。

1. [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) で、Office 365 全体の管理者アカウントを使用してサインインします。
    
2. ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。
    
3. [**Office 365 グループ**] を選択します。
    
     ![Office 365 グループ](media/authorize-guest-image2.png)
  
4. 組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するか否かに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。 [**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。 このトグルを**オン**にすると、グループおよびチームの所有者が組織外のユーザーを Office 365 グループおよび Microsoft Teams に追加できるかどうかを制御するための別のオプションが表示されます。 グループおよびチームの所有者がゲスト ユーザーを追加できるようにする場合は、このトグルを**オン**に設定します。 
 
   ![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/authorize-guest-image3.png)

上記の設定は、テナント レベルで適用され、Office 365 グループおよび Microsoft Teams でのゲストのエクスペリエンスを制御します。

グループのゲスト アクセスの詳細については、「[Office 365 グループのゲスト アクセス](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」を参照してください。ゲスト アクセスの仕組み、ゲスト アクセスの管理方法、よくある質問への回答が記載されています。

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online と OneDrive for Business へのゲスト アクセスを管理する

Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。  
   
Teams のゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。

- SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**
    
    詳細については、「[SharePoint Online 環境の外部共有を管理する](https://docs.microsoft.com/sharepoint/external-sharing-overview)」を参照してください。
    
- Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**
    
    詳細については、上記の「[Office 365 グループのゲスト アクセスを管理する](#control-guest-access-in-office-365-groups)」を参照してください。
  
上記の設定は、テナント レベルで適用され、SharePoint Online、OneDrive for Business、Office 365 グループおよび Teams でのゲストのエクスペリエンスを制御します。

Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。 詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。

## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]