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
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: チームまたは IT 管理者は、他のドメイン (フェデレーション) の外部アクセスを設定して、これらのドメインのユーザーが Teams に参加できるようにすることができます。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 071bb1523a0840a798edfe030a1dd52362695df2
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753532"
---
<a name="manage-external-access-in-microsoft-teams"></a>Microsoft Teams で外部アクセスを管理する
======================================================

外部アクセスは、外部の Teams ユーザーが Teams で自分との会議を検索、通話、チャット、セットアップできるようにするための1つの方法です。 また、外部アクセスを使用して、まだ Skype for Business (オンラインおよびオンプレミス) および Skype (2020 より前のリリース) を使用している外部ユーザーと通信することもできます。

外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。 外部アクセスとゲストアクセスの違いの詳細については、「外部アクセスと[ゲストアクセスの比較](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)」を参照してください。 

外部アクセスは、次の場合に使用します。
  
- 共同作業する必要があるさまざまなドメイン内にユーザーがいる。 たとえば、Rob@contoso.com と Ann@northwindtraders.com は、contoso.com と northwindtraders.com のドメインで、他のユーザーと一緒にプロジェクトで作業します。

- 組織内のユーザーが特定の組織外の会社のユーザーと連絡する際に、Teams を使用させたい場合。

- ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。 




> [!IMPORTANT]
> 現在、Microsoft Teams アプリ内で、まだ Azure Active Directory (Azure AD) またはテナントのゲストではない外部ユーザーとのフェデレーションを行うには、ハイブリッドに適切に設定して、Skype for Business Online に移行する必要があります。 2019年2月25日時点では、チームは、SIP プロフィールのユーザが Skype for Business Online をホームにしていなくても、ネイティブフェデレーションをサポートしていません。 ハイブリッド用にアカウントを設定し、Teams に移行する方法については、「 [Skype For business のハイブリッド展開を teams にアップグレードする](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)」を参照してください。






## <a name="plan-for-external-access"></a>外部アクセスの計画

既定では、外部アクセスは Teams で有効になっています。つまり、組織がすべての外部ドメインと通信できることを意味します。 ブロックしたドメインを追加すると、その他のすべてのドメインが許可されます。また、許可されたドメインを追加すると、他のすべてのドメインがブロックされます。 Teams 管理センターで外部アクセスをセットアップするには、次の3つのシナリオがあります (**組織全体の設定** > の**外部アクセス**)。

- **[フェデレーションを開く**]: これは Teams の既定の設定であり、組織内のユーザーは、任意のドメインで組織外のユーザーとの会議を検索、通話、チャット、セットアップすることができます。

    このシナリオでは、ユーザーは、チームまたは Skype for Business を実行していて、開いているフェデレーションを使用しているか、ドメインを許可リストに追加しているすべての外部ドメインと通信できます。

- [**特定のドメインを許可**する]:**許可**リストにドメインを追加して、許可されているドメインのみに外部アクセスを制限します。 許可ドメインのリストを設定すると、他のすべてのドメインがブロックされます。 特定のドメインを許可するには、[**ドメインの追加**] をクリックし、ドメイン名を追加して、[**このドメインで実行する操作**] をクリックし、[**許可**] を選びます。

- **特定のドメインをブロック**する-ドメインを**ブロック**リストに追加することで、ブロックしたドメイン*以外*のすべての外部ドメインと通信できます。 特定のドメインをブロックするには、[**ドメインの追加**] をクリックし、ドメイン名を追加して、[**このドメインで実行するアクション**] をクリックし、[**ブロック**] を選択します。 ブロックしたドメインのリストを設定すると、他のすべてのドメインが許可されます。

## <a name="allow-or-block-domains"></a>ドメインを許可またはブロックする

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>手順 1-組織が別のチーム組織と通信できるようにする

![Microsoft teams](media/teams-logo-30x30.png)**管理センターを使用し**た microsoft teams ロゴを示すアイコン  

1. 左側のナビゲーションで、[**組織全体の設定**]  >  [**外部アクセス**] に移動します。

2. ユーザーが**Skype For business および Teams ユーザーと通信できる**ように切り替え**ます。**

     ![外部アクセススイッチがオンになっているスクリーンショット](media/manage-external-access-2.png).

3. すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。

4. 組織内のユーザーと通信できる組織を制限する場合は、一部のドメインを除くすべてのドメインを許可するか、特定のドメインのみを許可することができます。 

    - 一部のドメインを除くすべてのドメインを許可するには、[**ドメインの追加**] をクリックして、ブロックするドメインを追加します。 [**ドメインの追加**] ウィンドウで、ドメイン名を入力し、[**禁止**] をクリックして、[**完了**] をクリックします。 
    - 特定の組織への通信を制限するには、[**許可**] の状態でそれらのドメインをリストに追加します。 許可リストにドメインを追加した後、他の組織との通信は、ドメインが許可リストに含まれる組織に限定されます。 

5. [**保存**] をクリックします。

6. 他のチーム組織の管理者がこれらの手順を完了していることを確認します。 たとえば、**許可ドメイン**リストでは、ユーザーとの通信を可能にする組織が制限されている場合は、管理者が自社のドメインに入力する必要があります。

### <a name="step-2---test-it"></a>手順 2-テストする

設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。
  
1. お客様ともう 1 つの組織の管理者が [**外部アクセス**] 設定の変更をそれぞれ完了すると、テストを開始できます。

2. Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。

3. お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。 相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。

4. ファイアウォールで問題があるかどうかをテストして、ファイアウォールの背後にない WiFi の場所に移動することもできます。 また、コーヒーショップなど、チームを使ってコンタクトにリクエストを送信して、チャットをすることができます。 メッセージは WiFi の場所で行われているが、仕事の途中ではない場合は、ファイアウォールに問題があることがわかります。

> [!NOTE]
> 自分と他のユーザーの両方が外部アクセスを有効にし、他のユーザーが1つのドメインを許可している場合は、これが有効になります。 問題が解決しない場合は、他のユーザーが自分のドメインをブロックしていないことを確認する必要があります。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Skype for Business Online の組織のユーザーとの通信

外部アクセスを設定して、チームユーザーが Skype for Business 組織のユーザーを検索し、ユーザーに連絡できるユーザーを制限する場合は、次の手順に従って、自分のドメインから別の組織のドメインに外部アクセスを設定します。 次に、他の組織の管理者に連絡して、Skype for Business Online の外部アクセスを構成するための手順を実行します。 

一般的な Skype for Business Online のシナリオに関する具体的なガイダンスについては、以下の[一般的な外部アクセスシナリオ](#common-external-access-scenarios)を参照してください。

**Skype for Business 管理センターを使って** ![Skype for Business のロゴを表示したアイコン](media/sfb-logo-30x30.png)

その組織の管理者に、次の手順を実行するよう依頼します。

1. Microsoft 365 管理センターで、[**管理センター** > **Teams & Skype** > **従来のポータル**] に移動します。
  
2. **Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。

3. 特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。

    または、Skype for Business のオープン ポリシーを使用する世界中の誰とでもユーザーが通信できるようにするには、[**禁止したドメインを除いてオンにする**] を選択します。 これは、既定の設定です。

4. [**禁止したドメインまたは許可**したドメイン] でを選ん**+** で、許可するドメインの名前を追加します。

## <a name="common-external-access-scenarios"></a>一般的な外部アクセスシナリオ

|**ご希望の場合**  |**操作**  |
|---------|-----------------------|
|組織内の**teams ユーザー**が別の (外部) 組織の**teams ユーザー**と通信できるようにします。|外部アクセスで、外部ドメインを許可リストに追加するか、[オープンフェデレーション] を使用します。 その後、他の Teams 組織の管理者にも同じことができます。      |
|組織内の**Teams ユーザー**が、同じ組織の**Skype for business Online ユーザー**と通信できるようにします。  |組織の Skype for Business ユーザーをサポートするには、[共存] モードを有効にするか、孤島アップグレードモードを選択します。   |
|組織内の**Teams ユーザー**が、別の (外部) 組織の**Skype for business Online ユーザー**と通信できるようにします。      |外部アクセスで、外部ドメインを許可リストに追加するか、[オープンフェデレーション] を使用します。 <br><br>[ユーザーが外部アクセスの**Skype For business および Teams ユーザー設定と通信できるよう**にする] をオンにします。 その後、他の Teams 組織の管理者にも同じことができます。 <br><br>**注**: Skype for business ユーザーの外部ドメインでは、その組織の Skype for business ユーザーをサポートするために、共存モードを有効にするか、孤島アップグレードモードを選択する必要があります。|
|組織内の**Teams ユーザー**が、組織内外の**Skype**ユーザーと通信できるようにします。   | このシナリオは近日中に公開されます。 <br><br>**重要**: チームユーザーは、まだ skype ユーザーと通信できませんが、Skype for business ユーザーは組織内外の skype ユーザーと通信できます。 **ユーザーが skype For business および Teams ユーザーと通信できるよう**にし、 **skype for Business ユーザーが外部アクセスの skype ユーザー設定と通信できるよう**にします。 |
|**Skype For Business Online ユーザー**が別の Office 365 組織の**Teams ユーザー**と通信できるようにします。| ユーザーが次のいずれかのアップグレードモード (孤島、SfBOnly、Sfbwithteams、SfBWithTeamsCollabAndMeetings、) を使用している場合は、Skype for Business Online ユーザーが別の組織の Teams ユーザーと通信できます。もう1つの組織の Teams ユーザーは、Teams の唯一のモードにあります。 <br><br>[ユーザーが外部アクセスの**Skype For business および Teams ユーザーと通信できるよう**にする] 設定をオンにします。 次に、他の Teams 組織の管理者にも同じことを行います。|
|Skype for **Business online ユーザー**が別の Office 365 組織の**Skype for business online ユーザー**と通信できるようにします。    | ユーザーが次のアップグレードモードのいずれかに該当する場合は、Skype for Business Online ユーザーが別の組織の Skype for Business Online ユーザーと通信することができます。これには、孤島、SfBOnly、Sfbwithteamab、SfBWithTeamsCollabAndMeetings;その他の組織の Skype for business Online ユーザーは、次のいずれかのアップグレードモード (孤島、SfBOnly Sfbwithteams SSfBWithTeamsCollabAndMeetings Ab、) にあります。<br><br>[ユーザーが外部アクセスの**Skype For business および Teams ユーザーと通信できるよう**にする] 設定をオンにします。 次に、他の Teams 組織の管理者にも同じことを行います。|
|**Skype For Business Online ユーザー**がオンプレミスの組織から**skype for business ユーザー**と通信できるようにします。     |ユーザーが次のアップグレードモードのいずれかを使用している場合、Skype for Business Online ユーザーは、オンプレミスの組織から Skype for business ユーザーと通信できます。これは、孤島、SfBOnly、Sfbwithteams SSfBWithTeamsCollabAndMeetings Ab、;その他の組織の Skype for business Online ユーザーは、次のいずれかのアップグレードモード (孤島、SfBOnly Sfbwithteams SSfBWithTeamsCollabAndMeetings Ab、) にあります。<br><br>[ユーザーが外部アクセスの**Skype For business および Teams ユーザーと通信できるよう**にする] 設定をオンにします。 次に、他の Teams 組織の管理者にも同じことを行います。|
|**Skype For Business Online ユーザー**が、組織内外の**skype ユーザー**と通信できるようにします。   |[ **Skype For business ユーザーが外部アクセスの skype ユーザーと通信できるよう**にします] 設定をオンにします。|
|組織内の**teams ユーザー**が組織外の**チームの無料ユーザー**と通信できるようにします。 | 無料版の Teams が外部アクセスとどのように連携するかについては、「 [Microsoft teams と Microsoft teams の相違点](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c)」を参照してください。|

> [!IMPORTANT]
> Teams または Skype for Business Online ユーザーが組織内外の Skype ユーザーと通信できるようにするために、 **skype ドメイン**を許可されたドメインとして追加する必要はありません。 すべての**Skype ドメイン**はホワイトリストに記載されています。つまり、これらのドメインはすべて許可されていると見なされます。



## <a name="how-does-external-access-compare-with-guest-access"></a>外部アクセスとゲストアクセスとの比較

外部アクセスとゲストアクセスの違いについては、「[他の組織のユーザーとの通信](communicate-with-users-from-other-organizations.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[外部 (フェデレーション) ユーザー向けのネイティブチャット操作](native-chat-for-external-users.md)