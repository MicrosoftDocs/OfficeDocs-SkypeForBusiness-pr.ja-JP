---
title: Microsoft Teams での外部アクセス (フェデレーション) の管理
author: LolaJacobsen
ms.author: lolaj
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
description: Teams または IT 管理者は、他のドメインの外部アクセス (フェデレーション) を構成して、それらのドメインのユーザーが Teams に参加できるようにすることができます。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 61ce8219125f6dad47ef516aa9f849acb09ec3dd
ms.sourcegitcommit: 87022aa009eae868e1fd945dc299367e16733a3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544993"
---
<a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams での外部アクセスの管理
======================================================

外部アクセスとは、ドメイン全体における外部の Teams ユーザーが Teams で会議の検索、呼び出し、チャット、設定を行うための手段です。 外部アクセスでは、Skype for Business (オンラインおよびオンプレミス) を現在使用している外部ユーザーや、Skype (プレビュー段階) を使用する外部ユーザーとも通信することができます。

外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。 外部アクセスとゲスト アクセスの違いの詳細については、「[外部アクセスとゲスト アクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。 

以下のような場合に外部アクセスを使用します。
  
- 別ドメインに共同作業が必要なユーザーがいる場合。 たとえば、Rob@contoso.com と Ann@northwindtraders.com が、contoso.com ドメインおよび northwindtraders.com ドメインの他のユーザーと一緒にプロジェクトの共同作業を行う場合です。

- 組織内のユーザーが、Teams を使用して組織外の特定の会社のユーザーに連絡する必要場ある場合。

- ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。 

> [!IMPORTANT]
> 現在、Microsoft Teams アプリ内で Azure Active Directory (Azure AD) またはテナントのゲストでない組織外の外部ユーザーへのフェデレーションを行うには、ハイブリッド環境を正しく設定し、Skype for Business Online に移行する必要があります。 2019 年 2 月 25 日現在、SIP プロフィールのユーザーが Skype for Business Online に属している場合を除き、Teams ではネイティブのフェデレーションはサポートされていません。 ハイブリッド環境でアカウントを設定した後に Teams に移行する場合の詳細については、「[Skype for Business のハイブリッド展開を Teams にアップグレードする](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)」を参照してください。

## <a name="plan-for-external-access"></a>外部アクセスの計画

Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。 禁止ドメインを追加すると、他のすべてのドメインが許可され、許可ドメインを追加すると、他のすべてのドメインが禁止されます。 Teams 管理センターで外部アクセスを設定するには、次の 3 つのシナリオがあります (**[組織全体の設定]**  >  **[外部アクセス]**)。

- **開いているフェデレーション**: これは Teams の既定の設定です。組織内のユーザーが任意のドメインの組織外ユーザーとの会議の検索、呼び出し、チャット、設定を行えるようにします。

    このシナリオでは、ユーザーはすべての外部ドメインと通信することができます。この外部ドメインは、Teams または Skype for Business を実行しており、開いているフェデレーションを使用しているか、ユーザーのドメインを許可リストに追加しています。

- **特定のドメインを許可する**: **[許可]** リストにドメインを追加して、外部アクセスを許可ドメインのみに制限します。 許可ドメインのリストを設定すると、他のすべてのドメインが禁止されます。 特定のドメインを許可するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[許可]** を選択します。

- **特定のドメインを禁止する** - **[禁止]** リストにドメインを追加すると、禁止したもの*以外の*すべての外部ドメインと通信することができます。 特定のドメインを禁止するには、**[ドメインの追加]** をクリックし、ドメイン名を追加します。その後、**[このドメインで実行するアクション]** をクリックし、**[禁止]** を選択します。 禁止ドメインのリストを設定すると、他のすべてのドメインが許可されます。

## <a name="allow-or-block-domains"></a>ドメインの許可または禁止

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>手順 1 - 組織が別の Teams の組織と通信できるように設定

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。

2. **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。

     ![[ユーザーは他の Skype for Business および Teams ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-2.png)。

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

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Skype for Business Online の組織のユーザーとの通信

Teams ユーザーへの連絡が制限されている Skype for Business 組織内のユーザーを、Teams ユーザーが検索して連絡できるように外部アクセスを設定するには、手順に従って、ドメインから他の組織のドメインへの外部アクセスを設定します。 そして、他の組織の管理者に、以下の手順に従って Skype for Business Online の外部アクセスを構成するよう依頼します。

一般的な Skype for Business Online のシナリオに関する具体的なガイダンスについては、下に記載されている「[一般的な外部アクセスのシナリオ](#common-external-access-scenarios)」を参照してください。

![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

その組織の管理者に、次の手順を実行するよう依頼します。

1. Microsoft 365 管理センターで、**[管理センター]**  >  **[Teams & Skype]**  >  **[従来のポータル]** の順に移動します。
  
2. **Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。

3. 特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。

    または、Skype for Business のオープン ポリシーを使用する世界中の誰とでもユーザーが通信できるようにするには、[**禁止したドメインを除いてオンにする**] を選択します。 これは、既定の設定です。

4. **[禁止したドメインまたは許可したドメイン]** の下で **[+]** を選択し、許可するドメイン名を追加します。

## <a name="communicate-with-skype-users-in-preview"></a>Skype ユーザーとの通信 (プレビュー段階)

組織内の Teams ユーザーが Skype ユーザーとチャットや通話をできるようにするには、次の手順を実行します。 この手順を実行すると、Teams ユーザーと Skype ユーザーとが、互いを検索したり、1 対 1 のテキストのみの会話や音声/ビデオ通話を開始したりできるようになります。

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、**[組織全体の設定]**  >  **[外部アクセス]** に移動します。

2. **[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。

    ![[ユーザーは Skype ユーザーと通信できます] 設定がオンになっているスクリーンショット](media/manage-external-access-5.png)。

Teams ユーザーと Skype ユーザーが通信できるようにする方法、および適用される制限事項の詳細については、「[Teams と Skype の相互運用性](teams-skype-interop.md)」を参照してください。

## <a name="common-external-access-scenarios"></a>一般的な外部アクセスのシナリオ

|**目的**  |**操作**  |
|---------|-----------------------|
|組織の **Teams ユーザー**が、別の (外部) 組織の **Teams ユーザー**と通信できるようにする。|外部アクセスで、外部ドメインを [許可] リストに追加するか、開いているフェデレーションを使用します。 他の Teams 組織の管理者にも同じ操作を行うように依頼します。      |
|組織の **Teams ユーザー**が、同じ組織の **Skype for Business Online ユーザー**と通信できるようにする。  |組織の Skype for Business ユーザーをサポートするには、共存モードを有効にするか、アイランドのアップグレード モードを選択します。   |
|組織の **Teams ユーザー**が、別の (外部) 組織の **Skype for Business Online ユーザー**と通信できるようにする。      |外部アクセスで、外部ドメインを [許可] リストに追加するか、開いているフェデレーションを使用します。 <br><br>外部アクセスの **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。 他の Teams 組織の管理者にも同じ操作を行うように依頼します。 <br><br>**注**: Skype for Business ユーザーの外部ドメインでは、その組織の Skype for Business ユーザーがサポートされるように、共存モードが有効になっているか、アイランドのアップグレード モードが選択されている必要があります。|
|組織の **Teams ユーザー**が、**Skype** ユーザーと通信できるようにする。<br> (プレビュー段階)  |外部アクセスの **[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。 |
|**Skype for Business Online ユーザー**が、他の Office 365 組織の **Teams ユーザー**と通信できるようにする。| ユーザーのアップグレード モードが、アイランド、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings のいずれかで、他の組織の Teams ユーザーが TeamsOnly モードの場合、Skype for Business Online ユーザーは他の組織の Teams ユーザーと通信することができます。 <br><br>外部アクセスの **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。 他の Teams 組織の管理者にも同じ操作を行うように依頼します。|
|**Skype for Business Online ユーザー**が、他の Office 365 組織の **Skype for Business Online ユーザー**と通信できるようにする。    | ユーザーのアップグレード モードが、アイランド、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings のいずれかで、他の組織の Skype for Business Online ユーザーのアップグレード モードが、アイランド、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings のいずれかである場合、Skype for Business Online ユーザーは他の組織の Skype for Business Online ユーザーと通信することができます。<br><br>外部アクセスの **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。 他の Teams 組織の管理者にも同じ操作を行うように依頼します。|
|**Skype for Business Online ユーザー**が、オンプレミス組織の **Skype for Business ユーザー**と通信できるようにする。     |ユーザーのアップグレード モードが、アイランド、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings のいずれかで、他の組織の Skype for Business Online ユーザーのアップグレード モードが、アイランド、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings のいずれかである場合、Skype for Business Online ユーザーはオンプレミス組織の Skype for Business Online ユーザーと通信することができます。<br><br>外部アクセスの **[Users can communicate with other Skype for Business and Teams users]**(ユーザーは他の Skype for Business および Teams ユーザーと通信できます) 設定をオンにします。 他の Teams 組織の管理者にも同じ操作を行うように依頼します。|
|**Skype for Business Online ユーザー**が、(組織内外の) **Skype ユーザー**と通信できるようにする。   |外部アクセスの **[ユーザーは Skype ユーザーと通信できます]** 設定をオンにします。|

> [!IMPORTANT]
> Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにする際、**Skype ドメイン**を許可ドメインとして追加する必要はありません。 すべての **Skype ドメイン**はホワイトリストに登録されており、これらのドメインはすべて許可されているものと見なされます。

## <a name="how-does-external-access-compare-with-guest-access"></a>ゲスト アクセスと比べて外部アクセスはどう違うのか

外部アクセスとゲスト アクセスの違いの詳細ついては、「[Microsoft Teams の別の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [外部 (フェデレーション) ユーザー向けのネイティブ チャット機能](native-chat-for-external-users.md)
