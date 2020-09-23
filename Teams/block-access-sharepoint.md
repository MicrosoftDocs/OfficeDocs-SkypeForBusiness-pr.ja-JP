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
description: 特定のユーザーの SharePoint へのアクセスをブロックする方法について説明します。
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203840"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>特定のユーザーの SharePoint へのアクセスをブロックする

Microsoft 365 の SharePoint で、条件付きアクセス (CA) ポリシーを適用することは、Teams にも適用されます。 ただし、一部の組織では、SharePoint ファイルへのアクセス (アップロード、ダウンロード、表示、編集、作成) を禁止していますが、従業員は、管理されていないデバイスで Teams のデスクトップ、モバイル、web クライアントを使用することを許可しています。 CA ポリシールールの下では、Sharepoint をブロックすると、チームもブロックされます。 この記事では、SharePoint に保存されているファイルへのアクセスを完全にブロックしながら、この制限を回避し、従業員がチームを引き続き使用できるようにする方法について説明します。

> [!Note]
> 非管理対象デバイスでアクセスをブロックまたは制限することは、Azure AD の条件付きアクセスポリシーに依存します。 [AZURE AD ライセンス](https://azure.microsoft.com/pricing/details/active-directory/)について説明します。 Azure AD での条件付きアクセスの概要については、「 [Azure Active Directory の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」を参照してください。 推奨される SharePoint Online access ポリシーの詳細については、「 [sharepoint サイトとファイルをセキュリティで保護するためのポリシー推奨事項](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。 管理対象外のデバイスでアクセスを制限する場合、管理対象デバイス上のユーザーは、 [サポートされている OS とブラウザーの組み合わせ](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)のいずれかを使用する必要があります。また、アクセスも制限されます。

次の場合に、アクセスをブロックまたは制限することができます。

- 組織内のユーザーまたは一部のユーザーまたはセキュリティグループのみ。

- 組織内のすべてのサイト、または一部のサイトのみ。

アクセスがブロックされると、ユーザーにエラーメッセージが表示されます。 アクセスをブロックすると、セキュリティが確保され、安全なデータを保護できます。 アクセスがブロックされると、ユーザーにエラーメッセージが表示されます。

1. SharePoint 管理センターを開きます。

2. [**ポリシー**  >  **アクセスポリシー**] を展開します。

3. [ **非管理デバイス** ] セクションで、[ **アクセスのブロック** ] を選択し、[ **保存**] を選択します。

   ![ポリシーの [管理されていないデバイス] セクション](media/no-sharepoint-access1.png)

4. [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)ポータルを開き、[**条件付きアクセスポリシー**] に移動します。

    次の例のような新しいポリシーが SharePoint によって作成されていることがわかります。

    ![ブラウザーアクセスに対してアプリで適用される制限という名前の新しいポリシー](media/no-sharepoint-access2.png)

5. 特定のユーザーまたはグループのみを対象とするようにポリシーを更新します。

    ![[ユーザーの選択] セクションが強調表示された Sharepoint 管理センター](media/no-sharepoint-access2b.png)

  > [!Note]
> このポリシーを設定すると、SharePoint 管理ポータルへのアクセスが切断されます。 除外ポリシーを構成して、グローバルと SharePoint の管理者を選択することをお勧めします。

6. ターゲットクラウドアプリとして SharePoint が選択されていることを確認する

    ![ターゲットアプリとして Sharepoint が選択されます。](media/no-sharepoint-access3.png)

7. **条件**を更新して、デスクトップクライアントを含めることもできます。

    ![デスクトップとモバイルアプリが強調表示されています。](media/no-sharepoint-access4.png)

8. **アクセス権の付与**が有効になっていることを確認する

    ![アクセス権の付与が有効になっています。](media/no-sharepoint-access5.png)

9. アプリに **適用** された制限の使用が有効になっていることを確認します。

10. ポリシーを有効にして、[ **保存**] を選択します。

    ![アプリで適用された制限が有効になっている。](media/no-sharepoint-access6.png)

ポリシーをテストするには、Teams デスクトップアプリや OneDrive for Business 同期クライアントなどの任意のクライアントからサインアウトし、もう一度サインインして、ポリシーが機能していることを確認する必要があります。 アクセスがブロックされている場合は、アイテムが存在しない可能性があるというメッセージが Teams に表示されます。

 !["アイテムは見つかりませんでした" というメッセージ。](media/access-denied-sharepoint.png)

Sharepoint では、アクセス拒否メッセージが表示されます。

![アクセス拒否メッセージ。](media/blocked-access-warning.png)

## <a name="related-topics"></a>関連項目

[SharePoint で管理されていないデバイスへのアクセスを制御する](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
