---
title: 特定のユーザーの SharePoint へのアクセスをブロックする
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 特定のユーザーの SharePoint へのアクセスをブロックする方法について説明します
ms.openlocfilehash: e3cda9d6443c41abc7dfa736be03555690a3b0f1
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615083"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>特定のユーザーの SharePoint へのアクセスをブロックする

Microsoft 365 の SharePoint の条件付きアクセス （CA） ポリシーを Teams に適用することもできます。 ただし、組織によっては、SharePoint ファイルへのアクセス （アップロード、ダウンロード、表示、編集、作成） をブロックし、従業員が非管理対象デバイスで Teams デスクトップ、モバイル、Web クライアントを使用できるようにしたいと考えています。 CA ポリシー ルールでは、SharePoint をブロックすると、Teams もブロックされます。 この記事では、この制限を回避し、SharePoint に保存されているファイルへのアクセスを完全にブロックしながら、従業員が Teams を引き続き使用できるようにする方法について説明します。

> [!Note]
> 非管理対象デバイスでのアクセスのブロックまたは制限は、Azure AD 条件付きアクセス ポリシーに依存します。 [Azure AD ライセンス](https://azure.microsoft.com/pricing/details/active-directory/) について説明します。 Azure AD 条件付きアクセスの概要については、「[Azure Active Directory の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」をご覧ください。 推奨される SharePoint Online アクセス ポリシーの詳細については、「[SharePoint サイトとファイルをセキュリティで保護するためのポリシーの推奨事項](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。 非管理対象デバイスでアクセスを制限すると、管理対象デバイス上のユーザーは [サポートされている OS とブラウザーの組み合わせ](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition) のいずれかを使用しなければならず、アクセスも制限されます。

次のアクセスをブロックまたは制限することができます:

- 組織内のユーザー、または一部のユーザーまたはセキュリティ グループのみ。

- 組織内のすべてのサイト、または一部のサイト。

アクセスがブロックされると、ユーザーにエラー メッセージが表示されます。 アクセスをブロックすると、セキュリティが強化され、データを保護できます。 アクセスがブロックされると、ユーザーにエラー メッセージが表示されます。

1. SharePoint 管理センターを開きます。

2. **[ポリシー]** > **[アクセス ポリシー]** を展開します。

3. **[非管理対象デバイス]** セクションで、**[アクセスのブロック]** を選択し、**[保存]** を選択します。

   ![ポリシーの非管理対象デバイス セクション](media/no-sharepoint-access1.png)

4. [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) ポータルを開き、**条件付きアクセス ポリシー** に移動します。

    次の例のような新しいポリシーが SharePoint によって作成されていることがわかります:

    !["ブラウザー アクセスにアプリによって適用される制限を使用する" という名前の新しいポリシー](media/no-sharepoint-access2.png)

5. 特定のユーザーまたはグループのみを対象とするようにポリシーを更新します。

    ![[ユーザーの選択] セクションが強調表示された SharePoint 管理センター。](media/no-sharepoint-access2b.png)

  > [!Note]
> このポリシーを設定すると、SharePoint 管理ポータルへのアクセスが制限されます。 除外ポリシーを構成し、グローバル管理者と SharePoint 管理者を選択することをお勧めします。

6. ターゲット クラウド アプリとして SharePoint のみが選択されていることを確認する

    ![ターゲット アプリとして SharePoint が選択されています。](media/no-sharepoint-access3.png)

7. デスクトップ クライアントも含めるように **条件** を更新します。

    ![デスクトップ アプリとモバイル アプリが強調表示されています。](media/no-sharepoint-access4.png)

8. **アクセス権の付与** が有効になっていることを確認する

    ![アクセス権の付与は有効になっています。](media/no-sharepoint-access5.png)

9. **[アプリによって適用される制限を使用する]** が有効になっていることを確認します。

10. ポリシーを有効にして、**[保存]** を選択します。

    ![アプリによって適用される制限は有効になっています。](media/no-sharepoint-access6.png)

ポリシーをテストするには、Teams デスクトップ アプリや OneDrive for Business 同期クライアントなどのクライアントからサインアウトし、再度サインインしてポリシーの動作を確認する必要があります。 アクセスがブロックされている場合は、アイテムが存在しない可能性があることを示すメッセージが Teams に表示されます。

 !["アイテムが見つかりません" というメッセージ。](media/access-denied-sharepoint.png)

SharePoint では、アクセスが拒否されたというメッセージが表示されます。

![アクセス拒否メッセージ。](media/blocked-access-warning.png)

## <a name="related-topics"></a>関連項目

[SharePoint で非管理対象デバイスのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
