---
title: 外部アクセス (フェデレーション) を管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
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
ms.openlocfilehash: ae9a198de7fa15ac77743b2477a44602e54fecb7
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421332"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams での外部アクセスの管理

外部アクセスは、外部ドメイン全体の Teams ユーザーが Teams で自分と会議を検索、通話、チャット、設定するための方法です。 また、外部アクセスを使用して、Skype for Business (オンラインおよびオンプレミス) および Skype (プレビュー) をまだ使用している他の組織のユーザーと通信できます。

他の組織のユーザーにチームやチャネルへのアクセスを許可する場合は、ゲスト アクセスの方が良い方法である可能性があります。 外部アクセスとゲスト アクセスの違いの詳細については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。 

以下のような場合に外部アクセスを使用します。
  
- 別ドメインに共同作業が必要なユーザーがいる場合。 たとえば、Rob@contoso.com と Ann@northwindtraders.com が、contoso.com ドメインおよび northwindtraders.com ドメインの他のユーザーと一緒にプロジェクトの共同作業を行う場合です。

- 組織内のユーザーが、Teams を使用して組織外の特定の会社のユーザーに連絡する必要場ある場合。

- ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。 

> [!IMPORTANT]
> Teams クライアントを使用して外部ユーザーと通信するには (そのユーザーが Teams または Skype for Business を使用している場合も)、Teams ユーザーは Skype for Business Online に保存されている必要があります。

## <a name="plan-for-external-access"></a>外部アクセスの計画

Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。 禁止ドメインを追加すると、他のすべてのドメインが許可され、許可ドメインを追加すると、他のすべてのドメインが禁止されます。 このルールの例外は、匿名参加者が会議で許可されている場合です。 Teams 管理センターで外部アクセスを設定するには、次の 3 つのシナリオがあります (**[組織全体の設定]**  >  **[外部アクセス]**)。

> [!NOTE]
> 組織で外部アクセスをオフにした場合でも、外部ユーザーは匿名参加を通じて会議に参加できます。 詳細については、「[Teams での会議設定を管理する](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)」を参照してください。

- **開いているフェデレーション**: これは Teams の既定の設定です。組織内のユーザーが任意のドメインの組織外ユーザーとの会議の検索、呼び出し、チャット、設定を行えるようにします。

    このシナリオでは、ユーザーはすべての外部ドメインと通信することができます。この外部ドメインは、Teams または Skype for Business を実行しており、開いているフェデレーションを使用しているか、ユーザーのドメインを許可リストに追加しています。

- **特定のドメインを許可する**: **[許可]** リストにドメインを追加して、外部アクセスを許可ドメインのみに制限します。 許可ドメインのリストを設定すると、他のすべてのドメインが禁止されます。 特定のドメインを許可するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[許可]** を選択します。

- **特定のドメインを禁止する** - **[禁止]** リストにドメインを追加すると、禁止したもの *以外の* すべての外部ドメインと通信することができます。 特定のドメインを禁止するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[禁止]** を選択します。 禁止ドメインのリストを設定すると、他のすべてのドメインが許可されます。

> [!NOTE]
> 許可されたドメインまたはブロックされたドメインは、会議への匿名アクセスが "オフ" の場合にのみ適用されます。

## <a name="allow-or-block-domains"></a>ドメインの許可または禁止

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>手順 1 - 組織が別の Teams または Skype for Business 組織と通信することを有効にする

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。

2. **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。

     ![[ユーザーは他の Skype for Business および Teams ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-2.png).

3. すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。

4. 組織内のユーザーと通信できる組織を制限するには、特定のドメイン以外のすべてを許可する方法と、特定のドメインのみを許可する方法があります。 

    - 特定のドメイン以外のすべてを許可するには、**[ドメインの追加]** をクリックして禁止するドメインを追加します。 **[ドメインの追加]** ウィンドウで、ドメイン名を入力して **[禁止]** をクリックし、**[完了]** をクリックします。 
    - 通信を特定の組織に制限するには、それらの組織のドメインを **[許可]** の状態でリストに追加します。 [許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。 

5. **[保存]** をクリックします。

6. 他の Teams の組織の管理者も同じ手順を実行したことを確認します。 たとえば、他のある組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、**許可ドメイン** のリストにお客様の会社のドメインを入力する必要があります。

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

次のセクションでは、一般的な外部アクセス シナリオでフェデレーションを有効にする方法、および TeamsUpgradePolicy が着信チャットと通話の配信を決定する方法について説明します。

### <a name="enable-federation"></a>フェデレーションを有効にする

組織内のユーザーが別の組織のユーザーと通信するには、両方の組織でフェデレーションを有効にする必要があります。 特定の組織のフェデレーションを有効にする手順は、組織が完全にオンラインか、ハイブリッドか、または純粋にオンプレミスかによって異なります。

|**組織が** |**次のようにフェデレーションを有効にする**  |
|:---------|:-----------------------|
|オンプレミスの Skype for Business がないオンライン。 これには、TeamsOnly ユーザーまたは Skype for Business Online ユーザーを持つ組織が含まれます。| Teams 管理センターを使用している場合: <br>- ユーザーが他の Skype for Business ユーザーと通信可能であり **、Teams** のユーザー設定が外部アクセスで有効になっているか確認します。<br>- オープン フェデレーション (他のドメインとのフェデレーションを許可する) を使用していない場合は、許可リストに外部ドメインを追加します。<br><br>PowerShell を使用している場合:<br>- テナントがフェデレーションに対して有効になっている必要があります `Get-CsTenantFederationConfiguration` `AllowFederatedUsers=true` 。 <br>- ユーザーの有効な値が `CsExternalAccessPolicy` . `EnableFederationAccess=true`<br>- オープン フェデレーションを使用していない場合は、ターゲット ドメインが `AllowedDomains` `CsTenantFederationConfiguration` |
|純粋なオンプレミス | オンプレミス ツールの場合: <br>- フェデレーションが有効になっているか確認します `CsAccessEdgeConfiguration` 。<br>- (グローバル ポリシー、サイト ポリシー、またはユーザーに割り当てられたポリシーを通じて) ユーザーのフェデレーション `ExternalAccessPolicy` が有効になっているか確認します。 <br> - オープン フェデレーションを使用していない場合は、ターゲット ドメインがリストに表示されるのを確認します `AllowedDomains` 。 |
|オンラインの一部のユーザー (Skype for Business または Teams) とオンプレミスの一部のユーザーとのハイブリッド。 | オンライン組織とオンプレミス組織の両方について、上記の手順に従います。 |

### <a name="delivery-of-incoming-chats-and-calls"></a>着信チャットと通話の配信 

フェデレーション組織からの着信チャットと通話は、TeamsUpgradePolicy の受信者ユーザーのモードに応じて、ユーザーの Teams または Skype for Business クライアントに配信されます。

|**必要な場合は、** |**次の操作を行います。**  |
|:---------|:-----------------------|
| 着信フェデレーション チャットと通話がユーザーの Teams クライアントに到着します。 | ユーザーを TeamsOnly に構成します。
| 着信フェデレーション チャットと通話がユーザーの Skype for Business クライアントに到着する | TeamsOnly 以外のモードでユーザーを構成します。 |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>組織内のユーザーと Skype のコンシューマー ユーザー間のフェデレーションを有効にする

組織内のユーザーと Skype のコンシューマー ユーザー間のフェデレーションを有効にするには、次の方法を使用します。

|**組織が** |**次のようにコンシューマー フェデレーションを有効にする**  |
|:---------|:-----------------------|
| オンプレミスの Skype for Business を使用した純粋なオンライン。  これには、TeamsOnly ユーザーまたは Skype for Business Online ユーザーを持つ組織が含まれます。 | Teams 管理センターを使用している場合: <br>-外部アクセス **でユーザーが Skype ユーザーと通信** 可能になっているか確認します。<br><br>PowerShell を使用している場合: <br>-テナントがフェデレーションに対して有効になっている必要があります `Get-CsTenantFederationConfiguration` `AllowPublicUsers=true` 。 <br> - ユーザーの有効な値が `CsExternalAccessPolicy` . `EnablePublicCloudAccess=true` |
| 純粋なオンプレミス | オンプレミス ツールの場合: <br> - Skype がフェデレーション パートナーとして有効に設定されています。 <br> - (グローバル ポリシー、サイト ポリシー、またはユーザー割り当てポリシーを使用して) ユーザー `EnablePublicCloudAccess=true` `ExternalAccessPolicy` を確認します。|
| オンラインの一部のユーザー (Skype for Business または Teams) とオンプレミスの一部のユーザーとのハイブリッド。| オンライン組織とオンプレミス組織の両方について、上記の手順に従います。


> [!IMPORTANT]
> Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにする際、**Skype ドメイン** を許可ドメインとして追加する必要はありません。 すべての **Skype ドメインが** 許可されます。

## <a name="how-does-external-access-compare-with-guest-access"></a>ゲスト アクセスと比べて外部アクセスはどう違うのか

外部アクセスとゲスト アクセスの違いの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [外部 (フェデレーション) ユーザー向けのネイティブ チャット機能](native-chat-for-external-users.md)
