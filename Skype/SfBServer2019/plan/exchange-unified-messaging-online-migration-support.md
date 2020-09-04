---
title: Exchange ユニファイド メッセージングの移行サポート
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft では、2020年2月28日に Exchange ユニファイドメッセージング Online (ExchUMO) サービスを廃止しています。 この記事では、影響を受けるお客様がビジネス継続性を計画する際に知っておく必要があることを要約しています。
ms.openlocfilehash: 5d7d9b2e488c61c881395ad00d2675d749e5e30f
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359303"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange ユニファイド メッセージングの移行サポート

> [!IMPORTANT]
> **Exchange Online のユニファイドメッセージングサービスは、2020年2月28日の午後太平洋時間にサポートされていません。すべてのボイスメールアカウントは、Microsoft によってクラウドボイスメールサービスに移行されました。残りの自動応答トラフィックは監視されず、いつでも中断する可能性があります。**

2019年2月8日の [アナウンス](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) への参照では、Microsoft は2020年2月28日に Exchange ユニファイドメッセージング Online (ExchUMO) サービスを廃止しています。 この記事では、影響を受けるお客様がビジネス継続性を計画する際に知っておく必要がある事項について概要を示します。

ExchUMO は、ボイスメール、自動応答、通話キュー、および fax 統合サービスのお客様によって展開されます。 Microsoft は、お客様が Skype for Business Online および Microsoft Teams で数千の顧客をサポートしている電話システムサービスへの移行を支援する計画を立てています。

ボイスメールは、主に Microsoft による移行です。お客様のサブセットについては、管理者の関与や投資が必要になる場合があります。 自動応答は、管理者主導の移行です。クラウド自動応答クラウドサービスで既存の ExchUMO 自動応答ツリーを再作成する必要があります。 サードパーティの PBX で任意の操作を使用しているお客様は、サードパーティの PBX システムをサポートしていないため、Skype cloud services に移行されません。 [このブログ](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)では、サードパーティサポートのための定年予定が発表されました。この展開モデルのお客様は、ユーザーを Microsoft の統合コミュニケーションプラットフォーム/サービスの1つに移行することも、サードパーティ製のボイスメールまたは自動応答ソリューションを取得することもできます。 Fax 統合は、クラウドベースのサービスではサポートされていません。お客様は、サードパーティ製のソリューションに移行する必要があります。

## <a name="who-is-affected"></a>影響を受けるユーザー

Exchange ユニファイドメッセージングオンラインサービスの次の機能のいずれかを使用しているお客様は影響を受けます。

- ボイスメールサービス
- 自動応答サービス
- 呼び出しキューサービス
- Fax 統合

> [!Note]
> オンプレミスの Exchange Server をユニファイドメッセージングで使用しているお客様は影響を受けません。

ユーザーと管理者がユーザーに及ぼす [影響](#user-experience-impact)についての詳細を確認してください。

## <a name="migration-plan-overview"></a>移行計画の概要

Microsoft は、独自の機能を使用しているさまざまな顧客展開を特定し、次のプランに基づいてお客様を移行することを支援しています。

|顧客グループ |タイムライン  |詳細  |
|---------|---------|---------|
|移行の準備ができているお客様<br><br>移行する機能:<br><ul><li>ボイスメール</ul>   |   3月-2019 年5月  |例:<ul><li>    シンプルなボイスメールの展開と使用状況を持つお客様<li>移行を実行するために Microsoft に対して確立されたすべての要件を持つお客様<ul>|
|前提条件を持つお客様<br><br>移行する機能:<br><ul><li>ボイスメール<li>自動応答<li>呼び出しキュー</ul> |  5月2019日 |例: <br><ul><li>ハイブリッド構成が完了していません<li>ハイブリッド PSTN 番号が設定されていない</ul>|
|お客様の投資 & 管理者の関与を必要とするお客様<br><br>移行する機能:<ul><li>voicemail<li>自動応答<li>呼び出しキュー<li>Fax 統合</ul>| 2020年2月までに  | 例: <br><ul><li>ExchUMO サービスは、サードパーティの PBX によって使用されています。<li>PSTN サブスクライバーアクセスの要件を持つお客様<li>SFB 2010 (未サポート) のお客様<li>Fax 統合</ul> |

## <a name="voicemail-migration-guidelines"></a>ボイスメール移行のガイドライン

### <a name="get-informed"></a>情報を入手する

ユーザーにとってスムーズな移行を計画するには、 [ブログのアナウンス](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) とこの記事をよくお読みください。 電話システムのボイスメール機能の詳細については、「 [Skype For business ボイスメールとオプションを確認](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) する」を参照してください。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Skype for Business ハイブリッドトポロジを確立する

Skype for Business ハイブリッドトポロジが確立されていない場合は、これを実行してボイスメールユーザーをスムーズに移行できるようにする必要があります。 詳細については、「 [Skype For business ハイブリッドの構成](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 」を参照してください。

> [!Note]
> ボイスメールサービスの移行のためにユーザーをオンラインで移行する必要はありません。 ただし、オンプレミスのユーザーが電話システムのボイスメールサービスを利用するには、ハイブリッドトポロジを確立する必要があります。

### <a name="plan-your-auto-attendant-migration"></a>自動応答の移行を計画する

管理者は、いつでも、ExchUMO からクラウドの自動応答への自動応答の移行を開始できます。 詳細について [は、「クラウド自動応答をセットアップする](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 」を参照してください。

Microsoft は、お客様が移行に必要と思われる追加の自動応答機能を引き続き提供しています。 管理者は、機能セットを評価し、それに応じて自動応答インスタンスを移行する必要があります。 機能リストの比較については、「 [Exchumo And Azure クラウドベースのサービス機能マトリックス](#exchumo-and-azure-cloud-based-services-feature-matrix)」を参照してください。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>移行後の検証とテストの計画

ボイスメールの移行は Microsoft によって行われます。 前提条件となるハイブリッドトポロジが確立されている場合、管理者は何もする必要はありません。 Microsoft は、ユーザーのボイスメールの移行が中断されないようにするために必要な検証とテストを行います。 管理者は、自分の側でテストと検証を行うことをお勧めします。 推奨されるテスト計画については、「提案された [テスト計画」および「管理者向けの移行後の検証](#suggested-test-plan-and-post-migration-validation-for-admins) 」を参照してください。

> [!Note]
> Lync Server 2010 はサポートされていません。 2010サーバー展開の場合は、サーバーのアップグレードを計画するか、ユーザーを Microsoft Teams に移行することを検討する必要があります。  

### <a name="monitor-the-admin-notification-center"></a>管理者通知センターを監視する

管理者通知センターの通知については、詳細とユーザーの移行に関するタイムラインを参照してください。 通知は、移行期間の少なくとも30日前に送信されます。

> [!Note]
> ユーザーの移行タイムラインで通知を受信し、業務上重要な理由で移行を延期したい場合は、Microsoft サポートに連絡してください。 2020年2月28日の退職日を超えて移行を延期することはできません。 さらに多くの質問があるお客様については、アカウントチームまたは Microsoft サポートにお問い合わせください。 Microsoft 365 または Office 365 をすでに使用しているお客様は、Microsoft 365 管理センターからサポート案件を送信できます。

### <a name="consider-opting-in-for-a-planned-migration"></a>計画された移行をオプトインすることを検討する

CVM への予定されたボイスメールサービスの移行を選択できます。 を有効にする前に、この記事の詳細を確認してください (特に次のセクションを参照してください)。

- 移行手順 (このセクション)
- ExchUMO および Azure クラウドベースのサービス機能のマトリックス
- ユーザー環境への影響

管理された移行を選択した場合、Microsoft 365 管理ポータルメッセージセンターでは、移行前の30日間の通知を受け取ることはありません。

計画された移行をオプトインするには、管理者の電子メールアドレスから、電子メール要求を [cvm@microsoft.com](mailto:cvm@microsoft.com) に送信して、次の情報を入力します。

- 推奨日 (火曜日): 移行 wave は毎週火曜日に実行されます。 12/3/2019 を超えていない火曜日の日付を選択してください。
 
- テナント ID:32 文字この形式の番号は、0046728c-688 a-4472-a38f-098fec60ac6x です。 テナント ID は、Microsoft 365 管理ポータルの Azure AD にあるか、または次の PowerShell コマンドレットを使用して見つけることができます。 `Get-CsTenant | Select ObjectId`

テナントが正常に移行されると、電子メールの確認が送信されます。

## <a name="auto-attendant-migration-guidelines"></a>自動応答移行のガイドライン

Microsoft 365 および Office 365 組織管理者は、Microsoft クラウド自動応答サービスで Exchange UM Online 自動応答を再作成して、オンプレミスの電話番号を、2020年2月28日の Exchange の UMO サービスの退職前に切り替える必要があります。 新しいクラウド自動応答を移行してテストするには、このガイドラインが推奨されています。 自動応答の数が多い場合は、 [EXCHANGE UM 自動応答をクラウド自動応答移行スクリプトに](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) 使用して、自動応答の一括移行を簡略化できます。

### <a name="auto-attendant-setup"></a>自動応答のセットアップ

過去1分の問題を回避し、クラウド自動応答サービスの機能や経験を理解するために、新しい自動応答のセットアップを早い段階で開始することを強くお勧めします。 1つ以上のギャップ機能を必要とする自動応答では、展開の準備にギャップ機能を使用できるときに、自動応答を作成してテストすることができます。 ギャップ機能の詳細については、 [付録](#appendix)を参照してください。

1. Exchange UMO コマンドレットを使用して、 [Get-Umautoアテンダント](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)を使用して既存の自動応答の構成をエクスポートします。  
2. Exchange Online の PowerShell で、コマンドレットの [export](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) を使用して、案内応答メディアファイル (使用されている場合) をエクスポートし、それを. mp3 形式に変換します。
3. Microsoft Teams の管理センターまたは Powershell を使用して自動応答を作成するには、「 [クラウド自動](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) 応答を計画する」の手順に従って、 [クラウド自動応答を設定](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) します。
4. メニューオプションが変更された場合は、案内応答を確認します。
5. この記事の「 [既知の問題](#known-issues) 」の「PSTN への自動応答呼び出しの転送」回避策を使用して、応答グループへの転送を構成します。  
6. 新しい自動応答をテストするには、それらを内部で呼び出すか、テスト電話番号を割り当てます。  

### <a name="cutover"></a>一括

1. 電話番号を Exchange UMO 自動応答から新しい自動応答に切り替えます。
2. SIP URI を連絡先オブジェクトからリソースアカウントに移動します。
3. 新たに割り当てられた電話番号を使用して、自動応答のテストと検証を行います。

## <a name="appendix"></a>付録

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO および Azure クラウドベースのサービス機能のマトリックス

| サービス | 機能レベル | 機能 | Notes  | クラウド VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| /VM  | サービス機能| サードパーティ製 PBX のサポート    | Exchange UM Online からの SIP notify メッセージを使用して、MWI (メッセージ待機インジケーター) などのサードパーティ製 PBX に提供されるすべての機能を含む | ×   | Y    |
| /VM | サービス機能  | Skype for Business Server をサポートする   |  | Y | Y    |
| /VM | サービス機能 | Microsoft Teams をサポートする|  | Y | ×    |
| /VM | サービス機能 | 電子情報開示と保持  | セキュリティと法令遵守  | Y | Y    |
| /VM | サービス機能 | Exchange ルールのサポート | セキュリティと法令遵守  | Y | Y    |
| /VM | ユーザー機能 | PSTN ダイヤルインアクセス  | サブスクライバーアクセス  | × | Y    |
| /VM | ユーザー機能 | 代理人  | 不在着信メール  | × | Y    |
| /VM | ユーザー機能 | PSTN Outlook Voice Access   | サブスクライバーアクセス  | × | Y    |
| /VM | ユーザー機能 | 認証されたエンドポイントを使用したダイヤルイン | ボイスメッセージを受信してボイスメールの設定を変更するためのボイスメールサービスの呼び出し| Y | Y    |
| /VM | ユーザー機能 | ボイスメールを無効にするためのユーザー設定   |  | Y | Y    |
| /VM | ユーザー機能 | 個人用の案内応答を変更するためのユーザー設定  |  | Y | Y    |
| /VM | ユーザー機能 | 不在時の案内応答を作成するためのユーザー設定  |  | Y | Y    |
| /VM | ユーザー機能 | 既定の言語を変更するためのユーザー設定  |  | Y | Y    |
| /VM | ユーザー機能 | TTS を使用して既定の案内応答を上書きするユーザー設定  |  | Y | ×    |
| /VM | ユーザー機能 | 個人用の案内応答の録音 (認証デバイス) |  | Y | Y    |
| /VM | ユーザー機能 | 個人用案内応答 (PSTN) の記録-電話での再生 |  | × | Y    |
| /VM | ユーザー機能 | 議事録を無効にするためのユーザー設定 |  | × | Y    |
| /VM | ユーザー機能 | 文字起こし  |  | Y | Y    |
| /VM | ユーザー機能 | SIP notify メッセージを使用した MWI (メッセージ待機インジケーター) |  | × | Y    |
| /VM | ユーザー機能 | Outlook での MP3 オーディオファイル形式    |  | Y | Y    |
| /VM | ユーザー機能 | 可変速度の再生コントロール |  | Y | Y    |
| /VM | ユーザー機能 | ボイスメールの転送  | 受信したボイスメールを他のユーザーに転送する | Y | Y    |
| /VM | ユーザー機能 | ユーザーのグループへの音声メッセージの送信  |ボイスメールブロードキャスト   | × | Y   |
| /VM | ユーザー機能 | SMS を使用したボイスメール通知    | ユーザーが新しいボイスメールを持っている場合は、SMS を受信できます。    | × | Y    |
| /VM | ユーザー機能 | サポートされる案内応答言語 | 詳細は次のとおりです。 https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| /VM | ユーザー機能 | 通話応答ルール |  | Y | Y    |
| /VM | ユーザー機能 | 電話での再生 (PSTN)-メッセージを再生する | 音声メッセージを聞くためにセルに電話をかける  | × | Y    |
| /VM | ユーザー機能 | 電話での再生 (認証)-メッセージを再生する | 認証されたデバイスでの呼び出し  | Y | Y    |
| /VM | ユーザー機能 | 複数のユーザー間の共有メールボックス |  | Y | Y    |
| /VM | 発信者の機能  | 発信者の利便性—保護されたボイスメール | 発信者は、録音済みのメッセージを保護されたものとしてマークするオプションを選択できます。| × | Y    |
| /VM | 発信者の機能  | 発信者の利便性-プライベートボイスメール | 発信者は、記録されたメッセージを親展としてマークするオプションを選択できます。  | × | Y    |
| /VM | 発信者の機能  | 無音検出   |  | × | Y    |
| /VM | テナント-管理機能 | サーバーレベルで保護されたボイスメール    | テナント管理者は、受信ボイスメールを保護としてマークするようにサービスレベルのルールを構成できます。 | Y | Y    |
| /VM | テナント-管理機能 | レコーディングの時間制限を変更する  |     | Y | Y    |
| /VM | テナント-管理機能 | 無音検出のタイムアウトを変更する    |  | 該当なし    | Y    |
| /VM | テナント-管理機能 | 入力エラーの数を変更する | CVM: 3 にハードコーディングされている | × | Y    |
| /VM | テナント-管理機能 | 既定の言語を変更する |  | Y | Y    |
| /VM | テナント-管理機能 | 議事録の無効化/有効化 |  | Y | Y    |
| /VM | テナント-管理機能 | 不在着信通知を無効または有効にする |  | × | Y    |
| /VM | テナント-管理機能 | ボイスメールプレビューの改善にご協力ください    |  | Y | Y    |
| /VM | テナント-管理機能 | 有効なユーザーのテキストメッセージをカスタマイズする|  | 該当なし    | Y    |
| /VM | テナント-管理機能 | 用語のプロファニティマスクの議事録|  | Y | ×    |
| /VM | テナント-管理機能 | ボイスメールポリシー    |   | Y | Y    |
| /VM | テナント-管理機能 | Web ポータルの管理   |  | CY19   | Y    |
| /VM | テナント-管理機能 | PowerShell   |  | Y | Y    |
| UM | ユーザー機能 | Skype for Business 認定電話機のメッセージ待機インジケーター (MWI)   |電話パートナーによって提供される場合がある  | いいえ | はい    |
| ナンバー | サービス機能 | AA はサードパーティの PBX をサポートします。    |  | × | Y    |
| ナンバー | サービス機能 | Skype for Business Server をサポートする   |  | Y | Y    |
| ナンバー | サービス機能 | Microsoft Teams をサポートする|  | Y | ×    |
| ナンバー | サービス機能 | 名前でダイヤルする、DTMF 入力    |  | Y | Y    |
| ナンバー | サービス機能 | 名前でダイヤル、音声入力  |  | Y | Y    |
| ナンバー | サービス機能 | 複数言語のサポート | 言語の詳細は次のとおりです。 https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| ナンバー | サービス機能 | オペレーター、CQ.ADD、またはユーザーへの転送 |  | Y | Y    |
| ナンバー | サービス機能 | PSTN 番号への内部転送 (DID RNL)  |  | Y | Y    |
| ナンバー | サービス機能 | PSTN 番号への外部への転送  |  | 下記の「既知の問題」セクションを参照してください。 | Y    |
| ナンバー | サービス機能 | 勤務時間 |  | Y | Y    |
| ナンバー | サービス機能 | メニューオプション | IVR メニューオプション  | Y | Y    |
| ナンバー | サービス機能 | Cloud PSTN 番号を AA に割り当てる |  | Y | ×    |
| ナンバー | サービス機能 | オンプレミスの PSTN 番号を AA に割り当てる  |  | Y | Y    |
| ナンバー | サービス機能 | カスタムユーザーの選択  | 発信者がカスタマイズされた組織ユーザーのリストに到達できるようにする| Y | Y    |
| ナンバー | サービス機能 | 勤務時間および休日の処置  |  | Y | Y    |
| ナンバー | サービス機能 | テキスト読み上げを使用したユーザー設定の案内応答  |  | Y | Y    |
| ナンバー | サービス機能 | 内線ダイヤル   | 内線番号をダイヤルしてユーザーに到達する  | Y   | Y    |
| ナンバー | サービス機能 | AA がメッセージを残すためのメールボックス    |  | Y   | Y    |
| ナンバー | サービス機能 | 複数の PSTN 番号の AA への割り当て|  | Y | Y    |
| ナンバー | テナント-管理機能 | Web ポータルの管理   |  | Y | ×    |
| ナンバー | テナント-管理機能 | PowerShell コマンドレット  |  | Y | Y    |
| FAX| サービス機能 | Fax 統合|  | × | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>管理者向けに推奨されるテスト計画と移行後の検証

ユーザーがクラウドボイスメールに移行されたことを確認するには、ボイスメールをユーザーに残し、Outlook でメッセージ本文を確認します。 クラウドボイスメールメッセージには、次のようなフッターがあります。

「議事録をご利用いただきありがとうございます。 上記のトランスクリプトが表示されない場合は、音声品質が議事録を作成するのに十分ではないためです。

ユーザーの移行後にボイスメール機能をテストする場合は、次のシナリオを考慮してください。

- 組織内のすべてのエンドポイントの種類 (アプリ、IP 電話など) でボイスメールアクセスを検証します。
- 構成したパーソナライズされた案内応答が発信者に対して再生されることをサンプルユーザーに対して検証します。
- ユーザーに対する議事録の使用を無効にする法的またはコンプライアンス要件が組織にある場合は、移行後に無効にすることを確認してください。 詳細については、「 [Cloud ボイスメールをセットアップ](/microsoftteams/set-up-phone-system-voicemail)する」を参照してください。
- 以前に Exchange VM のポリシーとルールを構成している場合は、それらが有効になっていることを確認してください。
- ユーザー設定を変更するためのクラウドボイスメールサービス PowerShell コマンドレットについて理解します。  

### <a name="user-experience-impact"></a>ユーザー環境への影響

エンドユーザーボイスメール移行の概要を次に示します。


|エクスペリエンス  |ユーザー環境での変更|
|---------|---------|
|メール通知 | 変更なし<br>ボイスメールアカウントのライセンス認証と移行についてユーザーに通知する電子メールは送信されません。 |
|以前のメッセージへのアクセス | 変更なし<br>ユーザーは、サポートされているすべてのエンドポイントの以前のボイスメールメッセージにアクセスできます。 |
|Outlook で VM を受信する、SFB アプリ| 変更なし<br>ユーザーは、サポートされているすべてのエンドポイントで引き続きボイスメールメッセージを受信します。 |
|文字起こし | 保護<br>CVM の議事録は、より高い精度率とサポートされている言語 (ExchUMO よりも) |
|ユーザー設定 | 新しい作業<br>ユーザーは、ユーザー設定ポータル (USP) からユーザー設定を変更することができます。 ユーザーは、ボイスメールのハイパーリンクから、または SFB クライアントの [ユーザー設定] ボタンを使用して、USP にアクセスできます。 https://aka.ms/vmsettings.
 |機能| 詳細については、「機能設定の比較」を参照してください。 |
|VM メッセージの Outlook ルール | 変更なし<br>以前に作成したルールは、移行後に CVM メッセージに適用されます。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM でのユーザー管理とプロビジョニング

新しい Skype for Business ユーザーは、作成時にクラウドボイスメール用に自動的にプロビジョニングされます。 新しいボイスメールユーザーをプロビジョニングするには、追加の管理作業またはライセンスは必要ありません。 既存および新規ユーザーのポリシー管理については、「 [クラウドボイスメールをセットアップ](/microsoftteams/set-up-phone-system-voicemail) する」を参照してください。

### <a name="admin-auto-attendant-management-experience"></a>管理者自動応答管理の手順

自動応答の詳細については、「 [クラウド自動応答の設定](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)」を参照してください。

### <a name="known-issues"></a>既知の問題

#### <a name="greeting-inconsistencies"></a>案内応答の不一致

すべてのユーザーがクラウドボイスメールに移行された後であっても、サービスが完全に廃止されるまで、サブスクライバーアクセスはテナントに対して引き続き動作する可能性があります。 ユーザーの混乱を防ぎ、一貫性のない動作を避けるために、移行後に案内応答が変更されたため、サブスクライバーアクセスを無効にします。 これを行うには、を使用して、各サブスクライバーアクセス回線の EXUM 連絡先を削除し `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` ます。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>PSTN への自動応答通話の転送

Skype for business server で Skype for Business Server または応答グループサービス (RG) 経由で外部 PSTN 電話番号に自動応答を転送するには、PSTN の電話番号または RG の電話番号に設定された着信転送を使用して、新しいオンプレミスのユーザーを作成します。 ユーザーはエンタープライズ Voip に対して有効であり、正しく構成されていて、音声ポリシーが割り当てられている必要があります。

#### <a name="shared-mailbox-is-still-accessible"></a>共有メールボックスにまだアクセスできる

Exchange UM Online を使用して構成された共有メールボックスは、CVM への移行後もメッセージを引き続き受信し、Outlook 経由でユーザーがアクセスできるようになります。 ただし、これらのメールボックスの案内応答メッセージを変更するためのアクセスは、CVM に移行した後は利用できません。 自動応答の発信者をキャプチャするために使用される共有メールボックスを持つお客様は、リリース後に、自動応答と通話キューの共有メールボックス機能を利用する必要があります (2019 年10月から)。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"ユーザー名が Skype for Business を使用していません" バナーが表示される

CVM サービスは Microsoft Teams インフラストラクチャに基づいており、Skype for Business クライアントからの呼び出しによって、"Username is は Skype for Business を使用していません。" という読み取りを行うクライアントに情報バナーが表示されることがあります。 操作性を向上させるには、Teams に切り替えるか、Skype 会議を開始してください。
このバナーが表示されないようにするために、ユーザーの Skype for Business クライアントを最新の C2R クライアント更新プログラムに更新してください。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>「音声メールをセットアップする」で OWA に移動します。

[クライアントからの **ボイスメールの設定** ] をクリックすると、cvm への移行後、Skype For business Server 2015/2013 のお客様は Office Web ACCESS (OWA) ポータルページに移動し続けます。 OWA の [ボイスメール] タブからすべての設定が削除され、ユーザーを CVM ユーザー設定ポータルに移動するリダイレクトリンクが付いたバナーが表示されます。

#### <a name="changing-greeting-remotely"></a>あいさつ文をリモートで変更する

CVM では、PSTN サブスクライバーアクセスはサポートされていません。 リモートで案内応答を変更する必要があるユーザーの場合は、モバイルクライアントのボイスメール IVR サービスに [案内応答の変更] メニューオプションが追加されています。 ユーザーは、モバイルクライアントのダイヤルパッドで "1" キーを押したままにして、このサービスを呼び出すことができます。
