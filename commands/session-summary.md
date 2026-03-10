# Session Summary Command

Bu session'da yapilanlari ozetle ve `.claude/tmp/session-[tarih].md` dosyasina kaydet.

## Ozet Sablonu

```markdown
# Session Ozeti — [tarih ve saat]

## Tamamlanan Isler
- [x] Feature/fix/refactor aciklamasi

## Devam Eden Isler
- [ ] Yarim kalan gorev

## Calisan Yaklasimlar (kanitlanmis)
- [Hangi approach ise yaradi ve neden]

## Denendi, Ise Yaramadi
- [Hangi approach basarisiz oldu ve neden]

## Onemli Teknik Kararlar
- [Mimari/teknik karar ve gerekcesi]

## Sonraki Adimlar
1. [Oncelik sirasiyla]
2.
3.

## Dikkat Edilmesi Gereken
- [Bilinen bug, edge case, teknik borc]

## Test Durumu
- Son test sonucu: PASS/FAIL
- Coverage: [%]
```

## Kullanim
Yeni session'a baslarken Claude'a sunu soyle:
"`.claude/tmp/session-[tarih].md` dosyasini oku ve kaldigin yerden devam et"
