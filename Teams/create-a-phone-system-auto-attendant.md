---
title: クラウドの自動応答をセットアップする
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Microsoft Teams のクラウド自動応答をセットアップしてテストする方法について説明します。
ms.openlocfilehash: 6ac4ccea48e70a8bba5e11511379fef5c5a2a861
ms.sourcegitcommit: e89c2234fc5aa8f7eeef66ba1ae093a0f7beda85
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "37349251"
---
# <a name="set-up-a-cloud-auto-attendant"></a>クラウドの自動応答をセットアップする

自動応答は、組織にコールインしているユーザーに対して、適切な部署、通話キュー、人、またはオペレーターにアクセスするためのメニューシステムの操作を許可します。 Microsoft Teams 管理センターを使用して、組織の自動応答を作成できます。 新しい自動応答を作成するには、左側のナビゲーションで [**音声**] に移動し、[**自動応答** > の**追加**] を選択します。

自動応答の詳細については、「[クラウド自動応答とは何ですか?](/microsoftteams/what-are-phone-system-auto-attendants) 」を参照してください。

> [!NOTE]
> この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。

## <a name="step-1--get-started"></a>手順 1-はじめに

- 自動応答には、関連するリソースアカウントが必要です。 必要なリソースアカウントとすべてのライセンスの詳細については、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。

> [!TIP]
> **電話システム**のライセンスを持つオンラインユーザーであるオペレーターまたはメニューオプションへの通話をリダイレクトするには、エンタープライズ voip に対して通話を有効にする必要があります。 「 [Skype For business ライセンスの割り当て](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」または「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。 Windows PowerShell を使用することもできます。 たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-a-new-auto-attendant"></a>手順 2-新しい自動応答を作成する

> [!IMPORTANT]
> 各自動応答には、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。 最初にリソースアカウントを作成してから、自動応答に関連付けることができます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

**Microsoft Teams 管理センター**で、[**音声** > **自動応答**] をクリックし、[ **+ 新規**] をクリックします。

#### <a name="general-info-page"></a>[一般的な情報] ページ

![[自分の自動応答] ページのスクリーンショット](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

**名前**自動応答のわかりやすい表示名を入力します。 名前の入力は必須で、空白を含む最大 64 文字を含めることができます。 [**自動応答**] タブの [**名前**] 列に表示されています。

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<a name="phonenumber"> </a>

**リソースアカウント**このボタンをクリックして、新しい自動応答に接続する1つ以上のリソースアカウントを選択します。 すべての自動応答には、リソースアカウントが関連付けられている必要があります。 リソースアカウントには、アカウントに関連付けられた電話番号を割り当てることができますが、電話番号は必須ではありません。 通常、トップレベルの自動応答には、電話番号が割り当てられているリソースアカウントがありますが、入れ子になった自動応答 (第2レベルの自動応答の接続先として使用されるレベル2のメニュー) には、リソースアカウントに割り当てられている電話番号がない場合があります。

* * *

![前のスクリーンショット](media/sfbcallout3.png)
 <a name="timezone"> </a>で吹き出しを参照している数値3のアイコン

**タイムゾーン**自動応答のタイムゾーンを設定する必要がありますが、組織に対して一覧表示されているメインアドレスのタイムゾーンに対応する必要はありません。 各自動応答には別のタイムゾーンを設定することができ、自動応答に設定された営業時間は、ここで選択したタイムゾーンに基づいて設定されます。

* * *

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

<a name="language"> </a>

**言語** 自動応答に使用する言語を、一覧表示されている使用可能な言語の中から選択します。 ここで設定した言語は、自動応答がこの自動応答を呼び出したユーザーとやり取りするために使用する言語です。また、すべてのシステムプロンプトはこの言語で再生されます。

* * *

![前のスクリーンショットで吹き出しを参照している数値5のアイコン](media/sfbcallout5.png)

<a name="operator"> </a>

**Operator**これは省略可能ですが、**オペレーター**のオプションを設定して、発信者がメニューから抜けて相手に向かって話すことができるようにすることができます。

既定では、0キーがオペレーターに割り当てられます。

オペレーターを設定した場合は、[**勤務時間の通話処理**] ページの [**編集] メニューのオプション**で、そのオプションについての通話相手にも通知する必要があります。 自動応答でオペレーターを設定した場合は、対応するメッセージテキストを [発信者に**聞こえる**] ボックスに入力するか、音声ファイルを変更してこのオプションを追加する必要があります。 たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。

オペレーターを設定するには、次のいくつかの方法があります。

- Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。

     > [!Note]
     > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。

- **音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。
- 通話相手がボイスメールに送信されるように設定できます。 これを行うには、[**社内の人**] を選択して、このユーザの着信をボイスメールに直接転送するように設定します。

* * *

![前のスクリーンショットで吹き出しを参照している番号6のアイコン](media/sfbcallout6.png)

**音声入力を有効にする**音声認識は、このオプションが選択されている場合に使用できます。 発信者は、[設定した言語](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)で音声入力を使用できます。 他のユーザーに電話機のキーパッドのみを使用させる場合は、音声認識をオフに設定することができます。

* * *

選択が完了したら、[**次へ**] をクリックします。

#### <a name="business-hours-page"></a>営業時間ページ

既定では、勤務時間は、月曜日から金曜日までの午前9:00 から 5:00 pm までに設定されています。 営業時間に含まれていないすべての時間は、業務時間外に考慮されます。 [24/7 の**選択**] をクリックして、すべての勤務時間を作成できます。 **[24/7 の選択**] オプションを選択しない限り、[**時間経過後の通話の設定**] ページが、自動応答の営業時間後の通話処理ルールの構成に使用されます。

![[勤務時間] ページのスクリーンショット](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

既定では、勤務時間は月曜日から金曜日の5:00 午前9:00 に設定されています。 スケジュールのすべての時間を選択解除するには、[**すべての時間をクリア**] オプションを選択します。 [**既定に戻す**] を選択すると、勤務時間は月曜日から金曜日まで、9:00 am ~ 5:00 pm にリセットされます。

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

稼働時間を変更するには、予定表に設定する勤務時間を強調表示します。 カレンダーでは、30分間隔で勤務時間を選択できます。ここで選択する業務時間は、[**一般情報**] ページで設定したタイムゾーンに基づいています。 休憩 (昼食休憩など) を設定するには、選択解除するか、カレンダーの時間を選択解除にドラッグします。 営業時間内に複数の休憩時間を設定できます。

* * *

選択が完了したら、[**次へ**] をクリックします。

#### <a name="business-hours-call-settings"></a>営業時間通話の設定

> [!TIP]
> 独自の勤務時間スケジュールを使用している場合は、[営業時間外通話の設定] ページを使用して、業務時間の経過に応じて発信**処理**を設定する必要があります。これにより、**営業時間通話の設定**と同じオプションが提供されます。

勤務時間中に組織の自動応答にリンクされた電話番号に通話を発信するときに、応答メッセージ、プロンプト、メニューを設定できます。

![営業時間の通話処理ページのあいさつ文](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![のスクリーンショット (勤務時間の通話処理ページアクションセクションのスクリーンショット)](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<a name="greetingsandrouting"> </a>

**あいさつ文**[勤務時間] 応答メッセージはオプションであり、**あいさつ文**に設定することはできません。 この場合、発信者は、選択したいずれかのアクションによって通話が処理される前に、メッセージまたは応答メッセージを読み上げません。 音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。
- **オーディオファイルをアップロードする**このオプションを選択した場合は、応答メッセージを録音して、音声ファイル (.wav、.mp3 または .wma 形式) をアップロードします。
- **あいさつ文を入力する**このオプションを選択する場合は、システムで読み取るテキスト (最大1000文字) を入力します。 たとえば、「Contoso へようこそ。 お電話ありがとうございます。 などと、[**発信者が聞く内容**] ボックスに入力できます。

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

営業時間中に着信する呼び出しに対する動作内容を選択できます。 次の操作から選ぶことができます。

<a name="redirectcalls"> </a>

- **切断** これを選択すると、発信者が営業時間の応答メッセージを聞いた後に切断されます。
- **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
  - Office 365 でエンタープライズボイスまたは割り当てられた通話プランに対応している**電話システム**のライセンスを持っている**会社のユーザー** 。 発信中のユーザーがボイスメールに送信されるように設定できます。 これを行うには、「**会社内のユーザ**」を選択し、ボイスメールに直接通話を転送するように設定します。

    > [!Note]
    > **会社内の**ユーザーは、Skype For business Server 2015 または Lync server 2013 を使用してオンプレミスでホストされているユーザーまたはオンラインユーザーになることができます。

   - その他の**自動応答**

   既存の自動応答を使って、サブメニューを含む第2レベルのメニューオプションを作成できます。 これらは入れ子の自動応答と呼ばれます。 ネストされた自動応答に通話を送信するには、[**会社内のユーザー** ] を選び、関連付けられた自動応答を既に持っているリソースアカウントか、この自動応答の作成が完了したら、自動応答に関連付ける1つのリソースアカウントを割り当てます。

- **[再生] メニューのオプション**を使って、再生するプロンプトを設定することもできます。

* * *

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

**メニュープロンプト**メインメニューのプロンプトを作成するには、音声合成を使用するか、音声ファイル (.wav、.mp3 または .wma) をアップロードします。 「**発信者のメニューナビゲーションを設定**する」ボックスにメッセージを入力するか、音声ファイルを録音して、たとえば「売上のために」、「話す、または1と言って」と言います。 サービスの場合は、2を押すか、2と発声します。 カスタマサポートについては、「3」または「3」と発声します。 演算子の場合は、0を押すか、0と発声します。 このメニューをもう一度読み上げるには、星のキーを押すか、「繰り返す」と発声します。 **あいさつ文を入力する**この設定を選択した場合は、システムが読み上げるテキスト (最大1000文字) を入力する必要があります。 **オーディオファイルをアップロードする**この設定を選択した場合は、応答メッセージを録音して、音声ファイル (.wav、mp3 または .wma 形式) をアップロードする必要があります。

* * *

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

**メニューオプションのセットアップ**キーボタンを使用したメニューオプションは、追加または削除できます。 メニューオプションを追加するには、 **+ enter キーを**押します。 対応するオプションの行が下に表示されます。 メニューオプションを削除するには、キーパッドコントロールで対応するキーの左側をクリックして、上の [削除] アイコンをクリックします。 キー マッピング行が削除されます。

> [!TIP]
> 削除オプションを追加するときに、既存のメニュープロンプトに対して自動的に実行されないため、メニュープロンプトテキストを更新するか、オーディオを個別に再録音する必要があります。  
>
>メニュー オプションはどのような順番でも追加、削除でき、キー マッピングは連続的である必要はありません。 たとえば、キー 2 を使用せず、キー 0、1、3 をオプションにマッピングしてメニューを作成することが可能です。

> [!NOTE]
> キー \* (繰り返し) と\# (戻る) は、システムによって予約されているため、再割り当てすることはできません。 音声認識が有効になっている場合、* を押すと「繰り返し」、# を押すと「戻る」の音声コマンドに対応します。

メニューオプションを設定するには、ダイヤルキーを選択した後、次の操作を行う必要があります。

- オプションの**音声コマンド**を入力します。 これは最大64文字で、"カスタマサービス" や "運営および根拠" などの複数の単語を含めることができます。 音声認識を有効にしている場合は、名前は自動的に認識されます。発信者は 3 を押すか、「さん」と音声入力するか、または 「顧客サービス」 と音声入力して、キー 3 にマッピングされたオプションを選択することができます。
- 対応するキーが押された場合に、通話を送信する場所を選択するか、音声認識を使ってオプションを選択します。 次の場所に呼び出しを送信できます。

  - **オペレーター** オペレーターがすでにセットアップされている場合は、キー 0 に自動的にマッピングされますが、削除するか別のキーに割り当てることもできます。 オペレーターがどのキーにも設定されていない場合は、音声コマンド 「オペレーター」 も無効になります。
  - Enterprise Voice で有効になっているか、Office 365 の通話プランを割り当てられている、**電話システム**のライセンスをもつ**社内の担当者** 発信中のユーザーがボイスメールに送信されるように設定できます。 そのためには、「**会社内のユーザ**」を選択し、ボイスメールに直接通話を転送するように設定します。

    > [!Note]
    > **会社内の**ユーザーは、Skype For business Server または Lync server 2013 を使用してオンプレミスでホストされているユーザーまたはオンラインユーザーになることができます。
    - その他の**自動応答**

       既存の自動応答を使って、サブメニューを含む第2レベルのメニューオプションを作成できます。 これらは入れ子の自動応答と呼ばれます。 ネストされた自動応答に通話を送信するには、[**会社内のユーザー** ] を選び、関連付けられた自動応答を既に持っているリソースアカウントか、この自動応答の作成が完了したら、自動応答に関連付ける1つのリソースアカウントを割り当てます。

        > [!Note]
        > 入れ子 (または第 2 レベル) の自動応答の **営業時間** も使用されます。これには、セットアップされた他の自動応答から送信された呼び出しへ向けたものも含まれます。

       - **音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。

* * *

![前のスクリーンショットで吹き出しを参照している数値5のアイコン](media/sfbcallout5.png)

**名前によるダイヤル** このオプションを選択すると、発信者はディレクトリ検索を使用して組織内の人を検索することができます。 [**ダイヤル スコープ**] ページでこれらのオプションをセットアップすることにより、名前によるダイヤルで誰が対応可能または対応不可として一覧表示されるのかを選択することができます。 **電話システム**のライセンスを持つオンラインユーザー、または Skype For business Server または Lync server 2013 を使用してオンプレミスでホストされているすべてのユーザーは、名前でダイヤルすることができます。

* * *

選択が完了したら、[**次へ**] をクリックします。

#### <a name="holiday-call-settings"></a>ホリデーシーズン通話の設定

各自動応答には、最大 20 個の決められた休業日を追加できます。

> [!TIP]
> **組織全体の設定** > の**休日**の画面に休日を作成したり、新しい通話ハンドラーの作成の一部として作成したりすることができます。

![[ホリデー通話の設定] ページのスクリーンショット](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

既に他の自動応答を作成している場合は、この一覧に表示されているオプションを使用したり、編集したりすることができます。 それ以外の場合は、新しい呼び出しハンドラーを作成する必要があります。

新しい通話ハンドラーを追加するには、[ **+ new call handler**] をクリックします。

* * *

![新しい通話ハンドラーの追加を示すスクリーンショット](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

新しいウィンドウで、画面の上部に新しい通話ハンドラーの名前を入力します。

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

休日の名前が、**休日**のプルダウンリストに既に存在している場合は、それを使うことができます。 必要な祝日の名前がまだ存在しない場合は、プルダウンリストで [新しい祝日の**作成**] を選択し、表示された新しい画面に新しい祝日の名前と日付を割り当てます。 準備ができたら、[**保存**] をクリックします。

休業日名は最大 64 文字で構成でき、同じ自動応答に対して一意である必要があります。 たとえば、同じ自動応答で 「感謝祭」という名前の休業日を 2 つもつことはできません。

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

**あいさつ文**応答メッセージは省略可能で**あり、あいさつ文**に設定することはできません。 この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。 音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。

- **応答なし**自動応答の電話番号に通話を発信しても、応答メッセージは再生されません。
- **オーディオファイルをアップロードする**このオプションを選択した場合は、休日の応答メッセージを録音して、音声ファイル (.wav、.mp3 または .wma 形式) をアップロードします。
- **あいさつ文を入力する**このオプションを選択する場合は、システムで読み取るテキスト (最大1000文字) を入力します。 たとえば、「あけましておめでとうございます。 当社は現在、休業中です。」 [**あいさつ文を入力**してください] ボックスを表示します。

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

**操作**この休日の間に到着した通話はどうなるかを選ぶことができます。 次のオプションから選択できます。

- **切断** 休業日の応答メッセージが流れてから、通話が切断されます。
- **呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。
  - Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。 発信中のユーザーがボイスメールに送信されるように設定できます。 そのためには、「**会社内のユーザ**」を選択し、ボイスメールに直接通話を転送するように設定します。

    > [!Note]
    > **社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。

   - **音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。

    > [!Note]
    > 既定では、休業期間中に着信したすべての呼び出しは、応答メッセージの後に切断されます。よって、違うビヘイビアーが望ましい場合には、リダイレクトを指定する必要があります。

#### <a name="select-dial-scope-page"></a>ダイヤルの範囲を選択ページ

このページでは、組織内のユーザーが自分の組織に電話をかけているユーザーに対して、自分のディレクトリに一覧表示され、名前でダイヤルできるように設定することができます。

![[ダイヤルの範囲] ページを示すスクリーンショット](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![数値1のアイコン。 [**含める**] オプションを使って、](media/sfbcallout1.png)前のスクリーンショットの吹き出しを参照するには、次の2つのオプションがあります。

- **すべての Online ユーザー** このオプションを使用すると、組織のすべてのユーザーがディレクトリ検索に含められます。 **電話システム**のライセンスを持っているすべてのオンラインユーザーと、Skype For business Server または Lync server 2013 を使用してオンプレミスでホストされ、Office 365 の通話プランを持っているユーザーが表示されます。
- **カスタムユーザーグループ**このオプションを使うと、組織内で作成された Office 365 グループ、配布リスト、またはセキュリティグループを検索できます。また、この Office 365 グループ、配布リスト、またはセキュリティグループに追加されたユーザーは **、** Skype For Business Server 2015 または Lync server 2013 を使用して、電話システムライセンスまたはオンプレミスでホストされている。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

[**除外**] オプションを使用する場合、次の2つのオプションがあります。

- **なし** このオプションを使用すると、いずれの Online ユーザーもディレクトリ検索から除外しません。
- **カスタムユーザーグループ**このオプションを使用すると、Office 365 グループ、配布リスト、または組織内で作成されたセキュリティグループを検索できます。この Office 365 グループ、配布リスト、セキュリティグループに追加されたすべてのユーザーは、ディレクトリ検索から除外されます。 複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。

> [!NOTE]
> 他のユーザーが音声認識で名前でダイヤルを使用している場合、新しいユーザーの名前がディレクトリに表示されるまでに最大36時間かかることがあります。

すべての必要なフィールドを入力し、通話処理のメニューとオプションを設定したら、[**送信**] をクリックします。

## <a name="editing-and-testing-auto-attendants"></a>自動応答の編集とテスト

自動応答を保存すると、[ **自動応答**] ページに表示されます。 これにより、設定したオプションの一部 (名前、電話番号、言語、状態など) をすばやく確認できます。

自動応答に変更を加える場合は、[自動応答] を選択し、[操作] ウィンドウで [**編集**] をクリックします。

操作ウィンドウの [**テスト**] ボタンを使用して、自動応答にテスト通話をすばやく配置することもできます。

## <a name="auto-attendant-cmdlets"></a>自動応答のコマンドレット

Windows PowerShell を使用して自動応答を作成し、設定することもできます。 自動応答を管理するために必要なコマンドレットを以下に示します。

- [新しい-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [CsAutoAttendant の入手](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [CsAutoAttendant の削除](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [新規-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [新しい-Csonline Audiofile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [新規-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [エクスポート-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [新規-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [インポート-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [新規-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Windows PowerShell の詳細について

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Office 365 および Microsoft Teams を管理することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell を使用する必要がある理由](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。

  - [Office 365 PowerShell で Office 365 を管理する](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>関連トピック

[Office 365 の電話システムでできること](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[サービス電話番号を取得する](/microsoftteams/getting-service-phone-numbers)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[クラウドの自動応答とは？](what-are-phone-system-auto-attendants.md)

[小規模ビジネスの例: 自動応答をセットアップする](/microsoftteams/tutorial-org-aa)  
