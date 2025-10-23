import React, { useState } from 'react';
import { motion } from 'framer-motion';
import { ShoppingCart, Globe, Phone, Star } from 'lucide-react';
import { Button } from '@/components/ui/button';

export default function AlManalStore() {
  const [lang, setLang] = useState('ar'); // اللغة الافتراضية عربية

  // النصوص باللغتين
  const content = {
    ar: {
      title: 'المنال للملابس النسائية',
      slogan: 'أناقة سودانية تليق بكِ',
      desc: 'تسوقي أحدث الثياب والعطور والإكسسوارات والشيلة من المنال',
      shopNow: 'تسوقي الآن',
      products: ['ثياب', 'عطور', 'إكسسوارات', 'شيلة'],
      testimonials: 'آراء عملائنا',
      review: 'خدمة رائعة وجودة ممتازة، تجربة تسوق ممتعة وسريعة!',
      customer: 'عميلة سعيدة',
      footer: '© 2025 المنال للملابس النسائية. جميع الحقوق محفوظة.',
      location: 'الرياض - المملكة العربية السعودية',
      phone: '+966 555 555 555',
      cart: 'السلة',
      langSwitch: 'عربي / EN',
    },
    en: {
      title: 'Al Manal Women’s Fashion',
      slogan: 'Sudanese elegance that suits you',
      desc: 'Shop the latest thobes, perfumes, accessories, and sheilas from Al Manal',
      shopNow: 'Shop Now',
      products: ['Thobes', 'Perfumes', 'Accessories', 'Sheilas'],
      testimonials: 'Customer Reviews',
      review: 'Excellent service and great quality! A wonderful shopping experience!',
      customer: 'Happy Customer',
      footer: '© 2025 Al Manal Women’s Fashion. All rights reserved.',
      location: 'Riyadh - Saudi Arabia',
      phone: '+966 555 555 555',
      cart: 'Cart',
      langSwitch: 'EN / عربي',
    },
  };

  const t = content[lang];

  return (
    <div
      className={`font-sans bg-white text-black min-h-screen ${
        lang === 'ar' ? 'text-right' : 'text-left'
      }`}
      dir={lang === 'ar' ? 'rtl' : 'ltr'}
    >
      {/* Header */}
      <header className="flex justify-between items-center p-4 shadow-md bg-white">
        <h1 className="text-2xl font-bold text-pink-500">{t.title}</h1>
        <div className="flex items-center gap-4">
          <Button
            variant="ghost"
            className="flex items-center gap-2"
            onClick={() => setLang(lang === 'ar' ? 'en' : 'ar')}
          >
            <Globe size={18} /> {t.langSwitch}
          </Button>
          <Button variant="outline" className="flex items-center gap-2">
            <ShoppingCart size={18} /> {t.cart}
          </Button>
        </div>
      </header>

      {/* Hero Section */}
      <motion.section
        initial={{ opacity: 0, y: 50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.8 }}
        className="bg-gradient-to-r from-pink-100 to-white py-20 text-center"
      >
        <h2 className="text-4xl font-bold mb-4 text-black">{t.slogan}</h2>
        <p className="text-gray-600 mb-6">{t.desc}</p>
        <Button className="bg-pink-500 text-white hover:bg-pink-600 text-lg px-6 py-3 rounded-2xl shadow-lg">
          {t.shopNow}
        </Button>
      </motion.section>

      {/* Products Section */}
      <section className="py-16 px-6 grid md:grid-cols-4 sm:grid-cols-2 gap-6">
        {t.products.map((cat, i) => (
          <motion.div
            key={i}
            whileHover={{ scale: 1.05 }}
            className="border rounded-2xl shadow-md overflow-hidden"
          >
            <img
              src={`https://source.unsplash.com/400x400/?${cat}`}
              alt={cat}
              className="w-full h-64 object-cover"
            />
            <div className="p-4 text-center">
              <h3 className="text-xl font-semibold text-pink-600">{cat}</h3>
              <Button variant="outline" className="mt-3">
                {lang === 'ar' ? 'عرض المنتجات' : 'View Products'}
              </Button>
            </div>
          </motion.div>
        ))}
      </section>

      {/* Testimonials */}
      <section className="bg-pink-50 py-12 text-center">
        <h3 className="text-2xl font-bold mb-6">{t.testimonials}</h3>
        <div className="flex justify-center flex-wrap gap-6">
          {[1, 2, 3].map((i) => (
            <div key={i} className="bg-white p-6 rounded-2xl shadow-md w-72"># Elmanal-store-
ثياب إكسسوارات عطور وكل المستلزمات النسائيه
