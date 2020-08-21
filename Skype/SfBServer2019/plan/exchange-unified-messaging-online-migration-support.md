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
description: Microsoft は、2020 年 2 月 28 日に Exchange ユニファイド メッセージング オンライン (ExchUMO) サービスを廃止しています。 この記事では、顧客に与える影響を要する要点を要め、また業務続きに関する計画を立ててまとめています。
ms.openlocfilehash: 587a6f0e17729181d7e0ba2389ed32faee07ff71
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824898"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange ユニファイド メッセージングの移行サポート

> [!IMPORTANT]
> **Exchange Online のユニファイド メッセージング サービスは、2020 年 2 月 28 日の PM 太 PM のポーシック タイムの範囲ではサポート外です。すべてのボイスメール アカウントは、Microsoft によって Cloud Voicemail サービスに移行されました。自動応答の残存トラフィックは監視されなくなります。いつでも中断される可能性があります。**

2019[announcement](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)年 2 月 8 日の発表に関して、Microsoft では 2020 年 2 月 28 日までに Exchange ユニファイド メッセージング オンライン (ExchUMO) サービスを廃止しています。 この記事では、影響を受けるお客様がビジネスの続き性を理解し、計画するための対応を要約した内容を取り上示します。

ExchUMO は、ボイスメール、自動応答、呼び出しキュー、および FAX 統合サービスのお客様によって展開されます。 Microsoft は、Skype for Business Online および Microsoft Teams で既に数種類のユーザーをサポートしている電話システム サービスへの移行をサポートするプランです。

ボイスメールは主に Microsoft 主体の移行です。顧客のサブセットでの関与や投資が必要な場合があります。 自動応答は管理に影響をきす移行です。クラウド サービスを使用する場合は、クラウド サービスに既存の ExchUMO 自動応答ツリーを再自動応答する必要があります。 サードパーティの PBX で ExchUMO 機能を使用するお客様は、サード パーティ製の PBX システムをサポートしていないため、Skype クラウド サービスに移行されません。 サードパーティ サポートの廃止計画はこのブログで通知されています。この展開モデルの[this blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)お客様は、Microsoft の統合コミュニケーション プラットフォーム/サービスにユーザーを移行したり、これらのユーザーに対してサードパーティのボイスメール/自動応答ソリューションを取得したりすることができます。 クラウドベースのサービスでは FAX 統合はサポートされていません。お客様はサード パーティのソリューションに移行する必要があります。

## <a name="who-is-affected"></a>影響を受けるユーザー

Exchange ユニファイド メッセージング サービスの以下のいずれかの機能を使用しているお客様が影響を受ける。

- ボイスメール サービス
- 自動応答 サービス
- 通話キュー サービス
- FAX 統合

> [!Note]
> オンプレミスのユニファイド メッセージングを使用Exchange Serverお客様には影響しません。

ユーザー エクスペリエンスへの影響へのユーザー エクスペリエンスや管理者エクスペリエン [スへの影響について詳しくは、次を参照してください](#user-experience-impact)。

## <a name="migration-plan-overview"></a>移行計画の概要

Microsoft は、さまざまなカスタマー展開を特定し、以下のプランに基づいてお客様の移行を支持しています。

|顧客グループ |タイムライン  |詳細  |
|---------|---------|---------|
|移行する準備が整っていない顧客<br><br>移行する機能:<br><ul><li>ボイスメール</ul>   |   2019 年 3 月~  |例:<ul><li>    単純なボイスメールの展開と使用状況を持つ顧客<li>マイクロソフトが移行を実行するためのすべての要件を満たしているお客様<ul>|
|必須コンポーネントを持つ顧客<br><br>移行する機能:<br><ul><li>ボイスメール<li>自動応答<li>コール キュー</ul> |  2019 年 5 月 - 12 月 |例: <br><ul><li>ハイブリッド構成が完了していません<li>ハイブリッド PSTN 番号が設定されていない</ul>|
|顧客への投資を必要と&関する顧客<br><br>移行する機能:<ul><li>voicemail<li>自動応答<li>通話キュー<li>FAX 統合</ul>| 2020 年 2 月  | 例: <br><ul><li>サード パーティ製 PBX によって利用される ExchUMO サービス<li>PSTN サブスクライバー アクセス要件を持つお客様<li>SFB 2010 の顧客 (サポート対象外)<li>FAX 統合</ul> |

## <a name="voicemail-migration-guidelines"></a>ボイスメールの移行ガイドライン

### <a name="get-informed"></a>情報を取得する

ユーザーのスムーズな移行 [を計画するには](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 、ブログのお知らせと記事の内容を理解しておきます。 電話 [システムのボイスメール機能の詳細については、「Skype for Business](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) ボイスメールを確認する」とオプションをご覧ください。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Skype for Business ハイブリッド トポロジの確立

Skype for Business のハイブリッド トポロジを確立していない場合は、ボイスメール ユーザーのスムーズな移行を可能にするために、この操作を行う必要があります。 詳細 [については、「Skype for Business ハイブリッドの構成](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 」を参照してください。

> [!Note]
> ボイスメール サービス移行のため、オンラインでユーザーを移行する必要はない。 ただし、社内ユーザーが電話システムのボイスメール サービスを利用するには、ハイブリッド トポロジを確立する必要があります。

### <a name="plan-your-auto-attendant-migration"></a>自動応答の移行を計画する

管理者は、いつでも自動応答の ExchUMO からクラウドへの移行を開始できます。 詳細 [については、「クラウドの自動応答をセットアップする」](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) を参照してください。

Microsoft は、お客様が移行に必要としていると考考す追加の自動応答機能を引き続き提供しています。 管理者は機能セットを評価して、自動応答インスタンスをその情報に従って移行する必要があります。 機能の一覧比較については [、ExchUMO および Azure のクラウドベースのサービス機能マトリックスを参照してください](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>ボイスメール移行後の検証とテストを計画する

ボイスメールの移行は Microsoft が行います。 前提条件のハイブリッド トポロジが確立されている場合、管理者は何もする必要はありません。 Microsoft は、必要な検証とテストを実行し、ユーザーのボイスメールの移行が中断されないことを確認します。 管理者は、並行してテストと検証を行お勧めします。 推奨 [されるテスト計画の場合は、管理者向けの推奨テスト計画と移行後](#suggested-test-plan-and-post-migration-validation-for-admins) の検証をご覧ください。

> [!Note]
> Lync Server 2010 はサポートされません。 サーバー展開の環境で、サーバーのアップグレードを計画するか、Microsoft Teams または Skype for Business Online へのユーザーの移行を検討してください。  

### <a name="monitor-the-admin-notification-center"></a>管理通知センターの監視

詳細およびユーザーの移行に関するタイムラインを付け、管理通知センターでお知らせをお知らせください。 少なくとも 30 日前に通知が送信されます。

> [!Note]
> ユーザーの移行タイムラインについての通知を受け取り、業務上重要な理由で移行を延期したい場合は、Microsoft サポートに連絡して移行を延期することができます。 廃止日 2020 年 2 月 28 日をもつだけを延期できません。 さらに質問がある場合は、アカウント チームまたは Microsoft サポートにお問い合わせください。 Microsoft 365 または Microsoft 365 を既に使用 Officeしているお客様は、Microsoft 365 管理センターからサポート ケースを送信できます。

### <a name="consider-opting-in-for-a-planned-migration"></a>計画した移行にオプトインを検討する

計画されたボイスメール サービスの CVM への移行をオプトインすることができます。 オプトインする前に、この記事の詳細 (特に以下のセクション) を確認してください。

- 移行手順 (このセクション)
- ExchUMO および Azure クラウドベースのサービス機能マトリックス
- ユーザー エクスペリエンスへの影響

管理移行を選択すると、移行前の 30 日間の通知が Microsoft 365 管理ポータル メッセージ センターに表示されません。

計画した移行の場合は、管理者のメール アドレスから次の情報を使用cvm@microsoft.com電子 [メール](mailto:cvm@microsoft.com) 要求を送信します。

- Preferred date (Tuesdays): migration waves are executed every Tuesday. 火曜日が 2019 年 12 月 3 日を上回りに設定しなけない日付を選びください。
 
- テナント ID: 0046728c-688a-4472-a38f-098fec60ac6x という形式の 32 文字の番号。 テナント ID は、Azure AD の Microsoft 365 管理ポータルで確認AD、または次の PowerShell コマンドレットを使用して検索できます。 `Get-CsTenant | Select ObjectId`

テナントが正常に移行されると、確認メールが送信されます。

## <a name="auto-attendant-migration-guidelines"></a>自動応答の移行のガイドライン

Microsoft 365 および Office 365 組織管理者は、Microsoft Cloud 自動応答 サービスで Exchange UM Online 自動応答を作成し直し、Exchange UMO サービスの廃止日 2020 年 2 月 28 日になる前に、この社内電話番号を切り替える必要があります。 これは、新しいクラウドの自動応答を正常に移行およびテストするために推奨されるガイドラインです。 自動応答の数が多い場合は [、Exchange UM 自動応答 をクラウド 自動応答](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) 移行スクリプトに使用すると、自動応答の一括移行を簡素化できます。

### <a name="auto-attendant-setup"></a>自動応答の設定

最前 1 分の問題を避け、クラウド 自動応答 サービスの機能とエクスペリエンスについて理解するために、新しい自動応答の設定を最初から開始しておくことを強くお勧めします。 ギップ機能が必要な自動応答の場合、展開の準備にギップ機能が用いう場合に、自動応答を作成し、テストできます。 ギップ機能の詳細については、「付録 [」を参照してください](#appendix)。

1. Exchange UMO コマンドレットを使用して [、Get-UMAutoAttendant を使用して既存の自動応答の構成をエクスポートします](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)。  
2. Exchange Online PowerShell [で Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) コマンドレットを使用して、案内応答メディア ファイルをエクスポートし, .mp3 形式に変換します。
3. クラウドの自動応答を [計画する手順に従](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) い [、](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) クラウド自動応答を設定し、Microsoft Teams 管理センターまたは Powershell を使用して、自動応答を作成します。
4. メニュー オプションが変更された場合は、案内応答を確認します。
5. この記事の既知の問題のセクションの「自動応答 Call Transfer to PSTN」回避策を使用して [応答グループへの転送](#known-issues) を構成します。  
6. 新しい自動応答を内部で発信するか、テスト用電話番号を割り当ててテストします。  

### <a name="cutover"></a>一括

1. 電話番号を Exchange UMO 自動応答から新しい自動応答に切り替える。
2. 連絡先オブジェクトからリソース アカウントへの SIP URI の移動。
3. 新しく割り当てられた電話番号を使用して、自動応答をテストし検証する。

## <a name="appendix"></a>付録

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO および Azure クラウドベースのサービス機能マトリックス

| サービス | 機能レベル | 機能 | Notes  | クラウド VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | サービス機能| サード パーティ製 PBX のサポート    | Exchange UM Online からの SIP 通知メッセージを使用して、MWI (Message Waiting Indicator) などのサード パーティ製 PBX に提供されるすべての機能が含まれる | N   | Y    |
| VM | サービス機能  | Skype for Business Server のサポート   |  | Y | Y    |
| VM | サービス機能 | Microsoft Teams をサポートする|  | Y | N    |
| VM | サービス機能 | 電子情報開示と保持  | セキュリティとコンプライアンスの場合  | Y | Y    |
| VM | サービス機能 | Exchange ルールのサポート | セキュリティとコンプライアンスの場合  | Y | Y    |
| VM | ユーザー機能 | PSTN ダイヤルイン アクセス  | サブスクライバー アクセス  | N | Y    |
| VM | ユーザー機能 | 代理人  | 不一着信メール  | N | Y    |
| VM | ユーザー機能 | PSTN Outlook Voice Access   | サブスクライバー アクセス  | N | Y    |
| VM | ユーザー機能 | 認証済みエンドポイントを使用するダイヤルイン | ボイスメール サービスを呼び出して音声メッセージを確認し、ボイスメール設定を変更する| Y | Y    |
| VM | ユーザー機能 | ボイスメールを無効にするユーザー設定   |  | Y | Y    |
| VM | ユーザー機能 | 個人用の案内応答を変更するユーザー設定  |  | Y | Y    |
| VM | ユーザー機能 | OOF 応答メッセージを作成するユーザー設定  |  | Y | Y    |
| VM | ユーザー機能 | 既定の言語を変更するユーザー設定  |  | Y | Y    |
| VM | ユーザー機能 | TTS で既定の案内応答を上書きするユーザー設定  |  | Y | N    |
| VM | ユーザー機能 | 個人用の案内応答を録音する (認証されたデバイス) |  | Y | Y    |
| VM | ユーザー機能 | 個人用案内応答の録音 (PSTN) — 電話での再生 |  | N | Y    |
| VM | ユーザー機能 | 文字の文字名を変更するユーザー設定 |  | N | Y    |
| VM | ユーザー機能 | 文字起こし  |  | Y | Y    |
| VM | ユーザー機能 | すべてのエンドポイントでのビジュアル ボイスメール   | サポートされているすべてのエンドポイントで再生、削除、メッセージ待機インジケーター、状態の切り替えを行います  | Y | Y    |
| VM | ユーザー機能 | Outlook の MP3 オーディオ ファイル形式    |  | Y | Y    |
| VM | ユーザー機能 | 可変速度再生コントロール |  | Y | Y    |
| VM | ユーザー機能 | ボイスメールを転送する  | 受信ボイスメールを他のユーザーに転送する | Y | Y    |
| VM | ユーザー機能 | ユーザーのグループに音声メッセージを送信する  |ボイスメール ブロードキャスト   | N | Y   |
| VM | ユーザー機能 | SMS を使用したボイスメール通知    | ユーザーは新しいボイスメールがある場合に SMS を受信できる    | N | Y    |
| VM | ユーザー機能 | サポートされている案内応答言語 | 詳細については、こちらを参照してください。 https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | ユーザー機能 | 通話応答ルール |  | Y | Y    |
| VM | ユーザー機能 | 電話での再生 (PSTN) でメッセージを再生 | このセルで電話して音声メッセージをリスンする  | N | Y    |
| VM | ユーザー機能 | 電話で再生 (Auth) メッセージ | 認証されたデバイスで電話してみ込み  | Y | Y    |
| VM | ユーザー機能 | 複数のユーザー間での共有メールボックス |  | Y | Y    |
| VM | 発信者機能  | 発信者エクスペリエンス — 保護されたボイスメール | 発信者は、録音されたメッセージを保護されているとマークするオプションを選択できます。| N | Y    |
| VM | 発信者機能  | 発信者エクスペリエンス — プライベート ボイスメール | 発信者は、録音されたメッセージをプライベートとしてマークするオプションを選択できます。  | N | Y    |
| VM | 発信者機能  | サイレンス検出   |  | N | Y    |
| VM | テナント管理機能 | サーバー レベルの保護されたボイスメール    | テナント管理者は、受信ボイスメールを保護対象としてマークするサービス レベル ルールを構成できます。 | Y | Y    |
| VM | テナント管理機能 | レコーディング期間の制限を変更する  |     | Y | Y    |
| VM | テナント管理機能 | シール検出のタイムアウトの変更    |  | N/A    | Y    |
| VM | テナント管理機能 | 変更回数の入力失敗 | CVM: 3 にハードコーデンデート | N | Y    |
| VM | テナント管理機能 | 既定の言語を変更する |  | Y | Y    |
| VM | テナント管理機能 | 文字名の文字名を無効/有効にする |  | Y | Y    |
| VM | テナント管理機能 | 不必要着信通知の無効/有効 |  | N | Y    |
| VM | テナント管理機能 | ボイス メールのプレビューの改善に Microsoft が役立つ    |  | Y | Y    |
| VM | テナント管理機能 | 有効なユーザー用のテキスト メッセージをカスタマイズする|  | N/A    | Y    |
| VM | テナント管理機能 | トランスクリプションの発表的マスキング|  | Y | N    |
| VM | テナント管理機能 | ボイスメール ポリシー    |   | Y | Y    |
| VM | テナント管理機能 | Web ポータルの管理   |  | CY19   | Y    |
| VM | テナント管理機能 | PowerShell   |  | Y | Y    |
| UM | ユーザー機能 | Skype for Business 認定された電話のメッセージ待機インジケーター (MWI)   |電話パートナーによって提供される可能性がある  | いいえ | はい    |
| AA | サービス機能 | AA によるサード パーティ製 PBX のサポート    |  | N | Y    |
| AA | サービス機能 | Skype for Business Server のサポート   |  | Y | Y    |
| AA | サービス機能 | Microsoft Teams をサポートする|  | Y | N    |
| AA | サービス機能 | 名前によるダイヤル、DTMF 入力    |  | Y | Y    |
| AA | サービス機能 | 名前によるダイヤル、音声入力  |  | Y | Y    |
| AA | サービス機能 | 複数言語サポート | 言語の詳細: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | サービス機能 | オペレーター、CQ、またはユーザーへの転送 |  | Y | Y    |
| AA | サービス機能 | 内部的に PSTN 番号への転送 (DID RNL)  |  | Y | Y    |
| AA | サービス機能 | 外部で PSTN 番号に転送する  |  | 以下の「既知の問題」セクションを確認する | Y    |
| AA | サービス機能 | 勤務時間 |  | Y | Y    |
| AA | サービス機能 | メニュー オプション | IVR メニュー オプション  | Y | Y    |
| AA | サービス機能 | クラウド PSTN 番号を AA に割り当てる |  | Y | N    |
| AA | サービス機能 | オンプレミス PSTN 番号を AAA に割り当てる  |  | Y | Y    |
| AA | サービス機能 | カスタム ユーザーの選択  | 発信者が組織ユーザーのカスタマイズされたリストに到達できる| Y | Y    |
| AA | サービス機能 | 勤務時間外と休日の調整  |  | Y | Y    |
| AA | サービス機能 | テキストから音声認識を使用したカスタムの案内応答  |  | Y | Y    |
| AA | サービス機能 | 内線ダイヤル   | ユーザーの内線番号をダイヤルしてユーザーに到達する  | Y   | Y    |
| AA | サービス機能 | AA 発信者がメッセージを残すメールボックス    |  | Y   | Y    |
| AA | サービス機能 | AA への複数の PSTN 番号の割り当て|  | Y | Y    |
| AA | テナント管理機能 | Web ポータルの管理   |  | Y | N    |
| AA | テナント管理機能 | PowerShell コマンドレット  |  | Y | Y    |
| FAX| サービス機能 | FAX 統合|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>管理者向けの推奨テスト計画と移行後の検証

ユーザーがクラウド ボイスメールに移行されたことを検証するには、ボイスメールをユーザーに残して Outlook でメッセージ本文を確認します。 クラウド ボイスメール メッセージには、次のものを見るフッターがあります。

「トランスクリ文字をお寄せいただきありがとうね。 上記のトランスクリプトが表示されない場合、音質が十分に透明でなかったので、これは品質が低い文字です。

ユーザーの移行後にボイスメールの機能をテストする場合は、次のシナリオを考慮してください。

- アプリや IP 電話など、組織内のすべてのエンドポイントの種類間でボイスメール アクセスを検証します。
- 構成されている案内応答が発信者に対して再生されていることをサンプル ユーザーに確認します。
- 組織にユーザーのトランスクリプションを無効にする法律またはコンプライアンス要件がある場合は、移行後に無効になっていることを確認してください。 詳細については、「クラウド ボイスメール [のセットアップ」を参照してください](/microsoftteams/set-up-phone-system-voicemail)。
- 以前に Exchange VM のポリシーとルールを構成している場合は、効果的なものを確認してください。
- ユーザー設定を変更するクラウド ボイスメール サービス PowerShell コマンドレットについて、十分に理解している。  

### <a name="user-experience-impact"></a>ユーザー エクスペリエンスへの影響

次に、エンドユーザーのボイスメール移行エクスペリエンスの概要を示します。


|エクスペリエンス  |ユーザー エクスペリエンスの変更|
|---------|---------|
|メール通知 | 変更なし<br>ボイスメール アカウントのアクティブ化/移行をユーザーに通知する電子メールは送信されません。 |
|前のメッセージにアクセスする | 変更なし<br>サポートされているすべてのエンドポイントで、以前のボイスメール メッセージにアクセスできます。 |
|Outlook での VM の受け取り、 SFB アプリ| 変更なし<br>ボイスメール メッセージは、サポートされるすべてのエンドポイントで引き続き受け取られます。 |
|文字起こし | 拡張<br>CVM トランスクリスションの精度はより高く、サポートされている言語は ExchUMO よりもはるかに高い精度です。 |
|ユーザー設定 | 新しいエクスペリエンス<br>ユーザーは、ユーザー設定ポータル (USP) からユーザー設定を変更できます。 ユーザーは、ボイスメール電子メールのハイパーリンクまたは SFB クライアントの [ユーザー設定] ボタンから、USP にアクセスできます。 https://aka.ms/vmsettings.
 |機能| 詳細については、機能セットの比較を参照してください。 |
|VM メッセージ用の Outlook ルール | 変更なし<br>以前に作成したルールは、移行後の CVM メッセージに適用されます。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM でのユーザー管理とプロビジョニング

新しい Skype for Business ユーザーは、作成されるとクラウド ボイスメールに対して自動的にプロビジョニングされます。 新しいボイスメール ユーザーのプロビジョニングには、追加の管理者の作業やライセンスは必要ありません。 既存 [および新規ユーザーのポリシー管理の](/microsoftteams/set-up-phone-system-voicemail) 詳細については、クラウド ボイスメールのセットアップを参照してください。

### <a name="admin-auto-attendant-management-experience"></a>管理自動応答エクスペリエンス

自動応答の詳細については、「クラウドの自動応答 [をセットアップする」を参照してください](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。

### <a name="known-issues"></a>既知の問題

#### <a name="greeting-inconsistencies"></a>案内応答の不一意性

すべてのユーザーを Cloud Voicemail に移行した後でも、サービスが完全に廃止されるまで、サブスクライバー アクセスはテナントに対して機能し続ける場合があります。 ユーザーの操作が乱なのを避けるため、案内応答が移行後変更されるので、サブスクライバー アクセスを無効にしてください。 これを行うには、使用している各サブスクライバー アクセスラインの EXUM 連絡先を削除します `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自動応答 PSTN への通話転送

Skype for Business Server または Skype for Business Server の応答グループ サービス (RGS) を介して外部 PSTN 電話番号に自動応答通話を転送するには、PSTN 電話番号または RGS 電話番号に通話転送を設定した新しいオンプレミス ユーザーを作成します。 ユーザーを有効にして正しく構成し、エンタープライズ VoIPポリシーが割り当てられていなけていなけずです。

#### <a name="shared-mailbox-is-still-accessible"></a>共有メールボックスはまだアクセス可能です

Exchange UM Online を使用して構成された共有メールボックスは、CVM への移行後もメッセージを受信し、Outlook 経由でユーザーがアクセスできるようになります。 ただし、これらのメールボックスの案内応答メッセージへのアクセスは、CVM に移行した後では使用できなくなります。 自動応答の発信者のキャプチャに使用されている共有メールボックスを使用するお客様は、リリース後に、自動応答および通話キュー共有メールボックス機能を活用する必要があります (2019 年 10 月)。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>「Username is not using Skype for Business」バナー の表示

CVM サービスは Microsoft Teams インフラストラクチャに基づいており、Skype for Business クライアントからの通話では、"ユーザー名は Skype for Business を使用していない" という情報バナーがクライアントに表示される場合があります。 エクスペリエンスを豊富にするために、Teams に切り替えるか、Skype 会議を開始してください。」
このバナーが表示されないように、ユーザーの Skype for Business クライアントを最新の C2R クライアント更新プログラムに必ず更新してください。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"ボイス メールのセットアップ" が OWA に移動する

クライアント **からのボイス メールの** 設定をクリックすると、CVM への移行後に引き続き Skype for Business Server 2015/2013 の顧客は Office Web Access (OWA) ポータル ページに移動します。 OWA の [ボイスメール] タブからすべての設定が削除され、ユーザーに CVM ユーザー設定ポータルへのリダイレクト リンクが表示されたバナーが表示されます。

#### <a name="changing-greeting-remotely"></a>リモートで案内応答を変更する

CVM では、PSTN サブスクライバー アクセスはサポートされていません。 リモートで案内応答を変更する必要があるユーザーの場合は、モバイル クライアント用のボイスメール IVR サービスに [案内応答の変更] メニュー オプションが追加されています。 ユーザーは、モバイル クライアントのダイヤルパッドで "1" キーを長押ししてこのサービスを呼び出できます。
