---
title: 外部アクセスの管理 (フェデレーション)
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: Teams または IT 管理者は、他のドメインの外部アクセス (フェデレーション) を構成して、それらのドメインのユーザーが Teams に参加できるようにすることができます。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a8139c01f5e79eab451abc1eb47a97c94849147a
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255420"
---
<a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams での外部アクセスの管理
======================================================

外部アクセスは、teams ユーザーが Teams で自分との会議を検索、通話、チャット、セットアップできるようにするための手段です。 また、外部アクセスを使用して、まだ Skype for Business (オンラインとオンプレミス) および Skype (プレビュー版) を使用している外部ユーザーと通信することもできます。

外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。 外部アクセスとゲスト アクセスの違いの詳細については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。 

以下のような場合に外部アクセスを使用します。
  
- 別ドメインに共同作業が必要なユーザーがいる場合。 たとえば、Rob@contoso.com と Ann@northwindtraders.com が、contoso.com ドメインおよび northwindtraders.com ドメインの他のユーザーと一緒にプロジェクトの共同作業を行う場合です。

- 組織内のユーザーが、Teams を使用して組織外の特定の会社のユーザーに連絡する必要場ある場合。

- ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。 

> [!IMPORTANT]
> Teams クライアントを使って外部ユーザーと通信するには (ユーザーが Teams または Skype for Business を使用しているかどうかにかかわらず)、Teams ユーザーが Skype for Business Online を使用している必要があります。

## <a name="plan-for-external-access"></a>外部アクセスの計画

Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。 禁止ドメインを追加すると、他のすべてのドメインが許可され、許可ドメインを追加すると、他のすべてのドメインが禁止されます。 Teams 管理センターで外部アクセスを設定するには、次の 3 つのシナリオがあります (**[組織全体の設定]**  >  **[外部アクセス]**)。

- **開いているフェデレーション**: これは Teams の既定の設定です。組織内のユーザーが任意のドメインの組織外ユーザーとの会議の検索、呼び出し、チャット、設定を行えるようにします。

    このシナリオでは、ユーザーはすべての外部ドメインと通信することができます。この外部ドメインは、Teams または Skype for Business を実行しており、開いているフェデレーションを使用しているか、ユーザーのドメインを許可リストに追加しています。

- **特定のドメインを許可する**: **[許可]** リストにドメインを追加して、外部アクセスを許可ドメインのみに制限します。 許可ドメインのリストを設定すると、他のすべてのドメインが禁止されます。 特定のドメインを許可するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[許可]** を選択します。

- **特定のドメインを禁止する** - **[禁止]** リストにドメインを追加すると、禁止したもの*以外の*すべての外部ドメインと通信することができます。 特定のドメインを禁止するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[禁止]** を選択します。 禁止ドメインのリストを設定すると、他のすべてのドメインが許可されます。

## <a name="allow-or-block-domains"></a>ドメインの許可または禁止

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>手順 1-組織が別のチームまたは Skype for Business 組織と通信できるようにする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。

2. **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。

     ![[ユーザーは他の Skype for Business および Teams ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-2.png).

3. すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。

4. 組織内のユーザーと通信できる組織を制限するには、特定のドメイン以外のすべてを許可する方法と、特定のドメインのみを許可する方法があります。 

    - 特定のドメイン以外のすべてを許可するには、**[ドメインの追加]** をクリックして禁止するドメインを追加します。 **[ドメインの追加]** ウィンドウで、ドメイン名を入力して **[禁止]** をクリックし、**[完了]** をクリックします。 
    - 通信を特定の組織に制限するには、それらの組織のドメインを **[許可]** の状態でリストに追加します。 [許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。 

5. **[保存]** をクリックします。

6. 他の Teams の組織の管理者も同じ手順を実行したことを確認します。 たとえば、他のある組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、**許可ドメイン**のリストにお客様の会社のドメインを入力する必要があります。

### <a name="step-2---test-it"></a>手順 2 - テスト

設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。
  
1. お客様ともう 1 つの組織の管理者が [**外部アクセス**] 設定の変更をそれぞれ完了すると、テストを開始できます。

2. Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。

3. お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。 相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。

4. ファイアウォールに問題があるかどうかをテストする別の方法は、ファイアウォールの外側の WiFi 環境に移動することです。 コーヒー ショップなどから、Teams を使用して連絡先にチャットの要求を送信します。 メッセージを WiFi 環境からは送信できるが、職場からは送信できない場合、問題の原因は職場のファイアウォールであることが特定できます。

> [!NOTE]
> これは、ユーザーともう 1 人のユーザーの両方が外部アクセスを有効にしてお互いのドメインを許可している場合に可能になります。 正常に動作しない場合は、もう 1 人のユーザーの構成でユーザーのドメインが禁止されていないかを確認してもらいます。


## <a name="communicate-with-skype-users-in-preview"></a>Skype ユーザーとの通信 (プレビュー段階)

組織内の Teams ユーザーが Skype ユーザーとチャットや通話をできるようにするには、次の手順を実行します。 この手順を実行すると、Teams ユーザーと Skype ユーザーとが、互いを検索したり、1 対 1 のテキストのみの会話や音声/ビデオ通話を開始したりできるようになります。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。

2. **[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。

    ![[ユーザーは Skype ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-5.png).

Teams ユーザーと Skype ユーザーが通信できるようにする方法、および適用される制限事項の詳細については、「[Teams と Skype の相互運用性](teams-skype-interop.md)」を参照してください。

## <a name="common-external-access-scenarios"></a>一般的な外部アクセスのシナリオ

以下のセクションでは、一般的な外部アクセスシナリオに対してフェデレーションを有効にする方法と、TeamsUpgradePolicy での着信チャットと通話の配信を決定する方法について説明します。

### <a name="enable-federation"></a>フェデレーションを有効にする

組織内のユーザーが別の組織のユーザーと通信できるようにするには、両方の組織がフェデレーションを有効にする必要があります。 特定の組織に対してフェデレーションを有効にする手順は、組織が純粋にオンライン、ハイブリッド、純粋にオンプレミスのいずれであるかによって異なります。

|**組織の場合** |**次のようにフェデレーションを有効にします。**  |
|:---------|:-----------------------|
|オンプレミスの Skype for Business がないオンライン。 これには、チームのユーザーまたは Skype for Business Online ユーザーがいる組織も含まれます。| Teams 管理センターを使用している場合: <br>-[外部アクセス] で [ **ユーザーが他の Skype For business および Teams ユーザーと通信できる** ようにする] 設定が有効になっていることを確認します。<br>-開いているフェデレーション (他のドメインとのフェデレーションを可能にする) を使用していない場合は、許可リストに外部ドメインを追加します。<br><br>PowerShell を使用している場合:<br>-テナントがフェデレーションに対して有効になっていることを確認します。 `Get-CsTenantFederationConfiguration` 表示する必要があり `AllowFederatedUsers=true` ます。 <br>-ユーザーの有効な値がにあることを確認し `CsExternalAccessPolicy` `EnableFederationAccess=true` ます。<br>-オープンフェデレーションを使用していない場合は、ターゲットドメインがに表示されていることを確認し `AllowedDomains` `CsTenantFederationConfiguration` ます。 |
|純粋なオンプレミス | オンプレミスツールでは、次の操作を行います。 <br>-でフェデレーションが有効になっていることを確認 `CsAccessEdgeConfiguration` します。<br>- `ExternalAccessPolicy` (グローバルポリシー、サイトポリシー、またはユーザーが割り当てられたポリシーのいずれかを通じて) ユーザーのフェデレーションを有効にします。 <br> -オープンフェデレーションを使用していない場合は、ターゲットドメインがに表示されていることを確認し `AllowedDomains` ます。 |
|一部のユーザー (Skype for Business または Teams のいずれか) とオンプレミスの一部のユーザーとのハイブリッド。 | オンラインとオンプレミスの両方の組織に対して、上記の手順を実行します。 |

### <a name="delivery-of-incoming-chats-and-calls"></a>チャットと通話の着信の配信 

フェデレーション組織からの着信チャットと通話は、TeamsUpgradePolicy の受信者ユーザーモードに応じて、ユーザーのチームまたは Skype for Business クライアントに表示されます。

|**目的** |**手順:**  |
|:---------|:-----------------------|
| フェデレーションされたチャットの着信と、ユーザーのチームクライアントで通話を受信できるようにします。 | ユーザーをチームのみに設定します。
| フェデレーションされたチャットの着信と、ユーザーの Skype for Business クライアントで通話を受信できるようにする | ユーザーは、TeamsOnly 以外のモードに設定します。 |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>組織内のユーザーと Skype のコンシューマーユーザーの間のフェデレーションを有効にする

組織内のユーザーと Skype のコンシューマーユーザーの間でフェデレーションを有効にするには、次の操作を行います。

|**組織の場合** |**次のようにコンシューマーフェデレーションを有効にする**  |
|:---------|:-----------------------|
| オンプレミスの Skype for Business を使用しない純粋なオンライン。  これには、チームのユーザーまたは Skype for Business Online ユーザーがいる組織も含まれます。 | Teams 管理センターを使用している場合: <br>-ユーザが **Skype ユーザとの通信が** 外部アクセスで有効になっていることを確認します。<br><br>PowerShell を使用している場合: <br>-テナントがフェデレーションに対して有効になっていることを確認します。 `Get-CsTenantFederationConfiguration` 表示する必要があり `AllowPublicUsers=true` ます。 <br> -ユーザーの有効な値がにあることを確認し `CsExternalAccessPolicy` `EnablePublicCloudAccess=true` ます。 |
| 純粋なオンプレミス | オンプレミスツールでは、次の操作を行います。 <br> -フェデレーションパートナーとして Skype が有効になっていることを確認します。 <br> - `EnablePublicCloudAccess=true` `ExternalAccessPolicy` (グローバルポリシー、サイトポリシー、またはユーザーによって割り当てられたポリシーを使用して) ユーザーを確認します。|
| 一部のユーザー (Skype for Business または Teams のいずれか) とオンプレミスの一部のユーザーとのハイブリッド。| オンラインとオンプレミスの両方の組織に対して、上記の手順を実行します。


> [!IMPORTANT]
> Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにする際、**Skype ドメイン**を許可ドメインとして追加する必要はありません。 すべての **Skype ドメイン**はホワイトリストに登録されており、これらのドメインはすべて許可されているものと見なされます。

## <a name="how-does-external-access-compare-with-guest-access"></a>ゲスト アクセスと比べて外部アクセスはどう違うのか

外部アクセスとゲスト アクセスの違いの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [外部 (フェデレーション) ユーザー向けのネイティブ チャット機能](native-chat-for-external-users.md)
