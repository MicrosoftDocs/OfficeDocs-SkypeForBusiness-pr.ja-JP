---
title: Microsoft Teams の情報障壁
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: この記事では、Microsoft Teams の情報障壁の概要と、チームへの影響について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2bbe2f38fe56e6952952730b7ba74dda1a98398f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904979"
---
# <a name="information-barriers-in-microsoft-teams"></a>Microsoft Teams の情報障壁

情報障壁 (IB) は、管理者が互いに連絡することを防止するために構成できるポリシーです。 これは、たとえば、ある部門が他の部署と共有する必要がない情報を処理している場合や、グループ外の人との通信を禁止または分離する必要がある場合に便利です。

> [!NOTE]
> - 情報バリアグループはテナント全体で作成できません。
> - ユーザーの追加にボットを使用することは、バージョン1ではサポートされていません。
> - プライベートチャネルは、構成する情報バリアーポリシーに準拠しています。
> - 新規: Teams に接続された SharePoint サイトの情報バリアのサポートは、現在プライベートプレビューになっています。 プライベートプレビューに参加するには、[ここ](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u)をクリックします。

情報バリアポリシーによって、検索と検出を防ぐこともできます。 つまり、通信しない相手と通信しようとしても、そのユーザーは [連絡先] 選択画面に表示されません。

## <a name="background"></a>背景

情報障壁の主要なドライバーは、金融サービス業界から提供されています。 金融業界規制機関 ([finra]( http://www.finra.org)) は、メンバー企業内での重要な情報の障壁と競合を確認し、そのような競合を管理する方法についてのガイダンスを提供します (finra 2241、[負債調査法通知 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)。  

ただし、情報の壁を取り入れるために、他の多くの領域で役に立つものが見つかりました。 その他の一般的なシナリオを以下に示します。

- 教育: ある学校の学生は、他の学校の学生の連絡先情報を検索することはできません。
- 法的: 1 つのクライアントによって得られたデータの機密性を、異なる顧客を表す同じ企業の弁護士によってアクセスされないようにします。
- 行政: 情報のアクセスと制御は、部門とグループで制限されています。
- プロフェッショナルサービス: 社内の複数のユーザーが、顧客契約中にフェデレーションまたはゲストアクセスでクライアントまたは特定の顧客とチャットすることができます。

たとえば、"プエルトリコ" は銀行口座に属し、Pradeep は財務アドバイザーセグメントに属します。 この2つのセグメント間の通信とコラボレーションは、組織の IB ポリシーによってブロックされるため、Pradeep とお互いの通信はできません。 ただし、Pradeep は、秀樹との通信を人事で行うことができます。

![セグメント間の通信を防止するための情報障壁を示す例](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>情報バリアを使用する状況

次のような状況では、情報バリアを使用することができます。

- チームは、特定の他のチームとデータのやり取りや共有を行うことができないようにする必要があります。
- チームは、チームの外部の人とデータをやり取りしたり、共有したりすることはできません。

情報バリアポリシー評価サービスは、通信が情報バリアポリシーに準拠しているかどうかを決定します。

## <a name="managing-information-barrier-policies"></a>情報バリアポリシーの管理

情報バリアポリシーは、PowerShell コマンドレットを使用して Microsoft 365 コンプライアンスセンター (SCC) で管理されます。 詳細については、「[情報バリアのポリシーを定義](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)する」を参照してください。

> [!IMPORTANT]
> ポリシーを設定または定義する前に、 **Microsoft Teams でスコープ指定されたディレクトリ検索を有効にする必要があり**ます。 スコープ指定されたディレクトリ検索を有効にしてから、情報バリアのポリシーを設定または定義する前に、少なくとも24時間待機します。 詳細に[ついては、「情報の障壁の前提条件」を参照して](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)ください。

## <a name="information-barriers-administrator-role"></a>情報障壁管理者の役割

IB コンプライアンス管理の役割は、情報バリアポリシーの管理を担当します。 この役割の詳細については、「 [Microsoft 365 コンプライアンスセンターの権限](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)」を参照してください。

## <a name="information-barrier-triggers"></a>情報バリアトリガー

以下の Teams イベントが発生すると、情報バリアポリシーが有効になります。

- **メンバーがチームに追加される**-ユーザーをチームに追加するときは、他のチームメンバーの情報バリアポリシーに対してユーザーのポリシーを評価する必要があります。 ユーザーが正常に追加されると、ユーザーはさらにチェックを行わなくても、チーム内のすべての機能を実行できます。 ユーザーのポリシーによってチームに追加されないようにブロックされている場合、ユーザーは検索に表示されません。

    ![グループチャットを示すスクリーンショット](media/information-barriers-add-members.png)

- **新しいチャットが要求**されました-2 人以上のユーザ間で新しいチャットがリクエストされるたびに、チャットが評価され、情報バリアポリシーに違反していないことが確認されます。 会話が情報バリアポリシーに違反した場合、その会話は開始されません。

    1:1 チャットの例を次に示します。

     ![1:1 チャットでのブロックされた通信を示すスクリーンショット](media/information-barriers-one-one-chat.png)

    グループチャットの例を次に示します。

    ![グループチャットを示すスクリーンショット](media/information-barriers-group-chat.png)

- **ユーザーが会議に参加するように招待され**ました-ユーザーが会議に参加するよう招待されたときに、ユーザーのポリシーが他のチームメンバーのポリシーに対して評価され、違反がある場合は、ユーザーが会議に参加することはできません。

    ![会議からブロックされたユーザーを示すスクリーンショット](media/information-barriers-meeting.png)

- **画面は、2人以上のユーザー間で共有され**ます。画面が2人以上のユーザーの間で共有されている場合は、他のユーザーの情報バリアポリシーに違反しないように画面共有を評価する必要があります。 情報バリアのポリシーに違反した場合、画面の共有は許可されません。
- **ユーザーがチームに電話による通話 (VOIP) を**行う-音声通話が他のユーザーまたはユーザーのグループによって開始されたときは、他のチームメンバーの情報バリアポリシーに違反していないことを確認するために、通話が評価されます。 違反が発生した場合、音声通話はブロックされます。
- **Teams のゲストユーザー** (情報バリアポリシー) は、teams のゲストユーザーにも適用されます。 組織のグローバルアドレス一覧でゲストユーザーを検出できるようにする必要がある場合は、「 [Microsoft 365 グループでゲストアクセスを管理](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#can-i-make-guest-objects-visible-in-the-global-address-list)する」を参照してください。 ゲストユーザーが検出可能になったら、[情報バリアポリシーを定義](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)できます。

## <a name="how-policy-changes-impact-existing-chats"></a>ポリシーの変更による既存のチャットへの影響

情報バリアポリシー管理者がポリシーに変更を加えた場合、またはユーザーのプロファイルが変更されたため (ジョブの変更や同様の理由で) ポリシーの変更が反映される場合、情報バリアポリシー評価サービスは、メンバーを自動的に検索して、チームのメンバーがポリシーに違反していないことを確認します。

ユーザー間に既存のチャットやその他の通信が存在し、新しいポリシーが設定されている場合、または既存のポリシーが変更されている場合、サービスは既存の通信を評価して、通信が引き続き許可されていることを確認します。

- **1:1 チャット**-2 人のユーザ間の通信が許可されなくなった場合 (ポリシーをブロックしている場合に、一方または両方のユーザーに対して通信がブロックされている場合)、チャットスレッドは読み取り専用になります。

- **グループチャット**-1 人のユーザーがグループに対して通信することが許可されなくなった場合 (たとえば、ユーザーがジョブを変更した場合など)、そのポリシーに違反した他のユーザーとの間でそのユーザーとの通信がグループチャットから削除される可能性があります。 ユーザーは以前の会話を見ることはできますが (この場合は読み取り専用)、グループとの新しい会話を表示したり、参加したりすることはできません。 新しいポリシーまたは変更されたポリシーによって複数のユーザーに通信が適用されない場合、ポリシーの影響を受けるユーザーはグループチャットから削除されることがあります。 以前の会話は引き続き表示されます。

この例では、Enrico が組織内の別の部門に移動され、グループチャットから削除されます。

  ![グループチャットを示すスクリーンショット](media/information-barriers-user-changes-job.png)

Enrico は、グループチャットにメッセージを送信することはできなくなりました。

  ![グループチャットを示すスクリーンショット](media/information-barriers-user-changes-job-2.png)

- **チーム**-グループから削除されたユーザーはチームから削除され、既存の会話または新規の会話を表示したり、新しい会話に参加したりすることはできなくなります。

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>シナリオ: 既存のチャットのユーザーがブロックされる

現在、情報バリアポリシーが別のユーザーをブロックしている場合、ユーザーは次のように操作します。

- [**連絡先] タブ**-ユーザーは [**連絡先**] タブでブロックされたユーザーを表示することはできません。
- **People picker** -ブロックされたユーザーは、people picker に表示されません。

    ![グループチャットを示すスクリーンショット](media/information-barriers-people-picker.png)
    
- **[アクティビティ] タブ**-ユーザーがブロックしたユーザーの [**アクティビティ**] タブにアクセスした場合、投稿は表示されません。 ([**アクティビティ**] タブには、チャネルの投稿のみが表示され、2人のユーザーに共通のチャネルはありません)。
- **組織**図-ブロックしたユーザーが表示されている組織図にユーザーがアクセスすると、ブロックしたユーザーは組織図に表示されず、代わりにエラーメッセージが表示されます。
- **連絡先カード**-ユーザーが会話に参加している場合、そのユーザーがブロックされたユーザーの名前の上にマウスポインターを置いたときに、他のユーザーには、連絡先カードの代わりにエラーメッセージが表示されます。 カードに記載されているアクション (通話やチャットなど) は利用できなくなります。
- **おすすめの連絡先**-ブロックされたユーザーは、おすすめの連絡先リスト (新規ユーザーに対して表示される最初の連絡先リスト) には表示されません。
- **チャットの連絡先**-ユーザーは、チャットの連絡先リストでブロックしているユーザーを確認できますが、ブロックされたユーザーは特定され、ユーザーが実行できる操作は、それらを削除することだけです。 ユーザーはそれをクリックして、過去の会話を表示することもできます。
- **連絡先**への通話-ユーザーは [着信] の連絡先リストでブロックされたユーザーを確認できますが、ブロックされたユーザーは特定され、ユーザーが実行できる操作は、それらを削除することだけです。
- **Skype から teams**への移行-Skype for Business から teams への移行中、すべてのユーザーは、情報バリアポリシーによってブロックされたユーザーを含めて teams に移行され、その後で説明したように処理されます。

## <a name="teams-policies-and-sharepoint-sites"></a>Teams のポリシーと SharePoint サイト

チームを作成すると、SharePoint サイトがプロビジョニングされ、ファイルエクスペリエンスのチームに関連付けられます。 この SharePoint サイトやファイルへのアクセスには、組織の IB のポリシーが適用されます。つまり、ib セグメントを持つユーザーのみがアクセスを許可します。 ファイル共有の時点でも、IB ポリシーは受け入れられます。

たとえば、Contoso Bank corporation では、ユーザー ' Sesha@contosobank.onmicrosoft.com ' は投資銀行取引セグメントに属し、ユーザー ' Nikita@contosobank.onmicrosoft.com ' はセグメント勧告に属しています。 この2つのセグメント間の通信とコラボレーションは、組織の IB ポリシーによってブロックされます。
ユーザーが、投資銀行取引先のチームを作成すると、そのチームとそれをバックアップした SharePoint サイトにアクセスできるのは、投資銀行セグメントのユーザーのみになります。 ユーザー Nikita は、サイトリンクを持っている場合でも、そのサイトにアクセスすることはできません。

## <a name="required-licenses-and-permissions"></a>必要なライセンスと権限

プランや価格などの詳細については、「[ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

## <a name="more-information"></a>詳細情報

- 情報の障壁の詳細については、「[情報の障壁](https://docs.microsoft.com/office365/securitycompliance/information-barriers)」を参照してください。

- 情報バリアポリシーを設定する方法については、「[情報バリアのポリシーを定義](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)する」を参照してください。

- 情報バリアポリシーを編集または削除するには、「[情報バリアポリシーを編集 (または削除)](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)する」を参照してください。
