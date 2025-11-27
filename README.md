import React, { useState } from 'react';
import { Menu, X, ArrowRight, Download, Printer, Heart, Star, ShoppingBag, Calendar, Mail, Instagram, Twitter, Facebook, Search, ChevronRight } from 'lucide-react';

export default function App() {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [cartCount, setCartCount] = useState(2);

  const toggleMenu = () => setIsMenuOpen(!isMenuOpen);

  return (
    <div className="min-h-screen bg-white font-sans text-stone-900 selection:bg-stone-900 selection:text-white">
      
      {/* Navigation */}
      <nav className="fixed w-full bg-white/95 backdrop-blur-sm z-50 border-b border-stone-100 transition-all duration-300">
        <div className="max-w-screen-2xl mx-auto px-6 lg:px-12">
          <div className="flex justify-between items-center h-24">
            {/* Desktop Menu - Left */}
            <div className="hidden md:flex items-center space-x-8 w-1/3">
              <a href="#shop" className="text-sm uppercase tracking-widest text-stone-500 hover:text-stone-900 transition-colors">Shop</a>
              <a href="#collections" className="text-sm uppercase tracking-widest text-stone-500 hover:text-stone-900 transition-colors">Collections</a>
              <a href="#about" className="text-sm uppercase tracking-widest text-stone-500 hover:text-stone-900 transition-colors">Journal</a>
            </div>

            {/* Logo - Center */}
            <div className="flex-shrink-0 flex items-center justify-center w-1/3 cursor-pointer">
              <span className="font-serif text-3xl tracking-tight text-stone-900">Paper & Plan</span>
            </div>
            
            {/* Icons - Right */}
            <div className="flex items-center justify-end space-x-6 w-1/3">
              <button className="text-stone-900 hover:text-stone-500 transition-colors hidden md:block">
                <Search className="w-5 h-5" strokeWidth={1.5} />
              </button>
              <button className="text-stone-900 hover:text-stone-500 transition-colors relative">
                <ShoppingBag className="w-5 h-5" strokeWidth={1.5} />
                <span className="absolute -top-1 -right-1 bg-stone-900 text-white text-[10px] font-medium w-4 h-4 rounded-full flex items-center justify-center">
                  {cartCount}
                </span>
              </button>
              <button onClick={toggleMenu} className="md:hidden text-stone-900 focus:outline-none">
                {isMenuOpen ? <X className="h-6 w-6" strokeWidth={1.5} /> : <Menu className="h-6 w-6" strokeWidth={1.5} />}
              </button>
            </div>
          </div>
        </div>

        {/* Mobile Menu Overlay */}
        {isMenuOpen && (
          <div className="md:hidden bg-white border-b border-stone-100 absolute w-full animate-fade-in-down z-40">
            <div className="px-6 py-8 space-y-6 flex flex-col items-center text-center">
              <a href="#shop" className="text-lg font-serif text-stone-900 hover:text-stone-500">Shop All</a>
              <a href="#collections" className="text-lg font-serif text-stone-900 hover:text-stone-500">Collections</a>
              <a href="#about" className="text-lg font-serif text-stone-900 hover:text-stone-500">Journal</a>
              <a href="#login" className="text-lg font-serif text-stone-900 hover:text-stone-500">Account</a>
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section className="pt-32 pb-20 lg:pt-48 lg:pb-32 px-6 lg:px-12 max-w-screen-2xl mx-auto">
        <div className="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div className="order-2 lg:order-1">
            <span className="block text-xs font-bold tracking-[0.2em] text-stone-400 uppercase mb-8">
              Est. 2024 — Digital Atelier
            </span>
            <h1 className="text-5xl lg:text-7xl font-serif text-stone-900 leading-[1.1] mb-8">
              Elevate your <br/>
              <span className="italic text-stone-500">daily ritual.</span>
            </h1>
            <p className="text-lg text-stone-600 mb-10 max-w-md font-light leading-relaxed">
              Curated digital stationery for the mindful professional. 
              Minimalist planners designed to bring clarity to chaos.
            </p>
            <div className="flex flex-col sm:flex-row items-start gap-6">
              <button className="px-10 py-4 bg-stone-900 text-white text-sm uppercase tracking-widest hover:bg-stone-800 transition-all w-full sm:w-auto">
                Shop Collection
              </button>
              <a href="#process" className="group px-6 py-4 flex items-center gap-2 text-stone-900 text-sm uppercase tracking-widest hover:text-stone-500 transition-colors">
                The Process <ChevronRight className="w-4 h-4 group-hover:translate-x-1 transition-transform" />
              </a>
            </div>
          </div>
          
          {/* Abstract Hero Visual - Minimalist Mockup */}
          <div className="order-1 lg:order-2 relative aspect-square lg:aspect-[4/5] bg-stone-50 flex items-center justify-center p-12 lg:p-24 overflow-hidden">
             {/* Main Page Mockup */}
             <div className="w-full h-full bg-white shadow-2xl shadow-stone-200/50 flex flex-col p-8 md:p-12 relative z-10 transition-transform duration-700 hover:scale-[1.02]">
                <div className="w-full h-full border border-stone-100 p-2 flex flex-col">
                  {/* Header of planner */}
                  <div className="flex justify-between items-baseline mb-12 border-b border-stone-100 pb-4">
                    <span className="font-serif text-2xl italic text-stone-900">2025</span>
                    <span className="text-xs uppercase tracking-widest text-stone-400">Weekly Overview</span>
                  </div>
                  {/* Grid lines */}
                  <div className="flex-1 space-y-8">
                    {[1,2,3,4].map(i => (
                      <div key={i} className="group">
                        <div className="flex justify-between mb-2">
                          <div className="w-32 h-1 bg-stone-100 group-hover:bg-stone-200 transition-colors"></div>
                        </div>
                        <div className="w-full h-[1px] bg-stone-100"></div>
                      </div>
                    ))}
                  </div>
                  {/* Footer */}
                  <div className="mt-auto pt-8 flex justify-between items-center text-[10px] text-stone-300 uppercase tracking-widest">
                    <span>Week 01</span>
                    <span>Paper & Plan</span>
                  </div>
                </div>
             </div>
             {/* Background Accent */}
             <div className="absolute top-0 right-0 w-2/3 h-full bg-stone-100/50 -z-0"></div>
          </div>
        </div>
      </section>

      {/* Minimal Features/Values */}
      <section id="process" className="py-24 border-t border-stone-100">
        <div className="max-w-screen-2xl mx-auto px-6 lg:px-12">
          <div className="grid grid-cols-1 md:grid-cols-3 gap-12 text-left">
            <div className="space-y-4">
              <span className="text-xs font-bold tracking-widest text-stone-400">01</span>
              <h3 className="font-serif text-xl text-stone-900">Instant Access</h3>
              <p className="text-stone-500 font-light text-sm leading-relaxed max-w-xs">
                Seamlessly delivered to your inbox immediately upon purchase. No shipping delays, ever.
              </p>
            </div>
            <div className="space-y-4">
              <span className="text-xs font-bold tracking-widest text-stone-400">02</span>
              <h3 className="font-serif text-xl text-stone-900">Thoughtful Design</h3>
              <p className="text-stone-500 font-light text-sm leading-relaxed max-w-xs">
                Every line, margin, and font is obsessed over to ensure maximum clarity and focus.
              </p>
            </div>
            <div className="space-y-4">
              <span className="text-xs font-bold tracking-widest text-stone-400">03</span>
              <h3 className="font-serif text-xl text-stone-900">Sustainable</h3>
              <p className="text-stone-500 font-light text-sm leading-relaxed max-w-xs">
                Zero physical waste. Print only what you need, when you need it, on the paper you love.
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Product Gallery */}
      <section id="shop" className="py-24 lg:py-32 bg-stone-50">
        <div className="max-w-screen-2xl mx-auto px-6 lg:px-12">
          <div className="flex flex-col md:flex-row justify-between items-end mb-20 gap-6">
            <div className="max-w-xl">
              <h2 className="text-4xl md:text-5xl font-serif text-stone-900 mb-6">The Collection</h2>
              <p className="text-stone-500 font-light text-lg">Functional tools designed for the modern minimalist.</p>
            </div>
            <a href="#" className="hidden md:block pb-1 border-b border-stone-900 text-sm uppercase tracking-widest hover:text-stone-600 hover:border-stone-400 transition-all">
              View All Products
            </a>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-8 gap-y-16">
            <ProductCard 
              title="The 2025 Master Planner"
              price="$24.00"
              type="Digital Bundle"
              imageStyle="bg-[#F5F5F4]" 
            />
            <ProductCard 
              title="Financial Clarity Kit"
              price="$18.00"
              type="Spreadsheets"
              imageStyle="bg-[#E7E5E4]" 
            />
            <ProductCard 
              title="Daily Focus Sheets"
              price="$12.00"
              type="Printable PDF"
              imageStyle="bg-[#FAFAFA]" 
            />
            <ProductCard 
              title="Wellness Journal"
              price="$16.00"
              type="Digital Planner"
              imageStyle="bg-[#F0F0F0]" 
            />
            <ProductCard 
              title="Academic Semester Pack"
              price="$20.00"
              type="Student Bundle"
              imageStyle="bg-[#EBEBEB]" 
            />
            <ProductCard 
              title="Meal & Nutrition Tracker"
              price="$14.00"
              type="Printable PDF"
              imageStyle="bg-[#F5F5F5]" 
            />
          </div>
          
          <div className="mt-16 text-center md:hidden">
            <button className="px-8 py-4 border border-stone-300 text-sm uppercase tracking-widest hover:bg-white transition-colors w-full">
              View All Products
            </button>
          </div>
        </div>
      </section>

      {/* Editorial / Break Section */}
      <section className="py-32 bg-stone-900 text-white overflow-hidden relative">
        <div className="absolute inset-0 opacity-20" style={{ backgroundImage: 'linear-gradient(#333 1px, transparent 1px), linear-gradient(90deg, #333 1px, transparent 1px)', backgroundSize: '40px 40px' }}></div>
        <div className="max-w-4xl mx-auto px-6 text-center relative z-10">
          <p className="text-sm font-bold tracking-[0.3em] text-stone-400 uppercase mb-8">Philosophy</p>
          <blockquote className="text-3xl md:text-5xl font-serif leading-tight mb-12">
            "Simplicity is the ultimate sophistication. We build tools that get out of your way."
          </blockquote>
          <div className="w-24 h-[1px] bg-stone-700 mx-auto"></div>
        </div>
      </section>

      {/* Newsletter */}
      <section className="py-24 bg-white border-t border-stone-100">
        <div className="max-w-xl mx-auto px-6 text-center">
          <h2 className="text-3xl font-serif text-stone-900 mb-4">The Sunday Edit</h2>
          <p className="text-stone-500 font-light mb-10">
            Join our inner circle for weekly organization tips, exclusive freebies, and early access to new collections.
          </p>
          <div className="flex flex-col gap-4">
            <input 
              type="email" 
              placeholder="Email Address" 
              className="w-full px-0 py-4 border-b border-stone-300 text-stone-900 placeholder:text-stone-400 focus:outline-none focus:border-stone-900 transition-colors bg-transparent text-center"
            />
            <button className="mt-4 px-8 py-4 bg-stone-900 text-white text-sm uppercase tracking-widest hover:bg-stone-800 transition-all w-full">
              Subscribe
            </button>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-white border-t border-stone-100 pt-20 pb-12">
        <div className="max-w-screen-2xl mx-auto px-6 lg:px-12">
          <div className="flex flex-col md:flex-row justify-between items-start gap-12 mb-20">
            <div className="max-w-sm">
              <span className="font-serif text-2xl tracking-tight text-stone-900 block mb-6">Paper & Plan</span>
              <p className="text-stone-400 font-light text-sm leading-relaxed">
                Refining the art of planning. <br/>
                Designed in Copenhagen, loved worldwide.
              </p>
            </div>
            
            <div className="flex flex-wrap gap-12 md:gap-24">
              <div>
                <h4 className="text-xs font-bold uppercase tracking-widest text-stone-900 mb-6">Shop</h4>
                <ul className="space-y-4 text-sm font-light text-stone-500">
                  <li><a href="#" className="hover:text-stone-900 transition-colors">New Arrivals</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Best Sellers</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Bundles</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Gift Cards</a></li>
                </ul>
              </div>
              <div>
                <h4 className="text-xs font-bold uppercase tracking-widest text-stone-900 mb-6">Support</h4>
                <ul className="space-y-4 text-sm font-light text-stone-500">
                  <li><a href="#" className="hover:text-stone-900 transition-colors">FAQ</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Contact</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Returns</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Privacy</a></li>
                </ul>
              </div>
              <div>
                <h4 className="text-xs font-bold uppercase tracking-widest text-stone-900 mb-6">Social</h4>
                <ul className="space-y-4 text-sm font-light text-stone-500">
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Instagram</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">Pinterest</a></li>
                  <li><a href="#" className="hover:text-stone-900 transition-colors">TikTok</a></li>
                </ul>
              </div>
            </div>
          </div>
          
          <div className="flex flex-col md:flex-row justify-between items-center pt-8 border-t border-stone-100 text-xs text-stone-400 uppercase tracking-widest">
            <p>© 2024 Paper & Plan.</p>
            <div className="flex gap-6 mt-4 md:mt-0">
               <a href="#" className="hover:text-stone-900">Terms</a>
               <span className="text-stone-300">|</span>
               <a href="#" className="hover:text-stone-900">Privacy</a>
            </div>
          </div>
        </div>
      </footer>
    </div>
  );
}

function ProductCard({ title, price, type, imageStyle }) {
  return (
    <div className="group cursor-pointer">
      <div className={`relative aspect-[3/4] ${imageStyle} overflow-hidden mb-6 transition-all duration-500`}>
        {/* Simple geometric product representation */}
        <div className="absolute inset-0 flex items-center justify-center p-12 opacity-90 group-hover:scale-[1.03] transition-transform duration-700 ease-out">
            <div className="w-full h-full bg-white shadow-xl flex flex-col p-6">
                <div className="w-full h-1/2 border-b border-stone-50 mb-4"></div>
                <div className="space-y-3">
                    <div className="w-full h-[1px] bg-stone-100"></div>
                    <div className="w-full h-[1px] bg-stone-100"></div>
                    <div className="w-full h-[1px] bg-stone-100"></div>
                    <div className="w-2/3 h-[1px] bg-stone-100"></div>
                </div>
            </div>
        </div>
        
        {/* Hover Action */}
        <div className="absolute inset-0 bg-stone-900/0 group-hover:bg-stone-900/5 transition-colors duration-300 flex items-end justify-between p-6 opacity-0 group-hover:opacity-100">
            <button className="bg-white text-stone-900 px-6 py-3 text-xs uppercase tracking-widest hover:bg-stone-900 hover:text-white transition-colors w-full shadow-lg">
                Add to Cart
            </button>
        </div>
      </div>
      
      <div className="space-y-1">
        <p className="text-xs font-bold tracking-widest text-stone-400 uppercase">{type}</p>
        <div className="flex justify-between items-baseline">
            <h3 className="text-lg font-serif text-stone-900 group-hover:text-stone-600 transition-colors">{title}</h3>
            <span className="text-sm font-medium text-stone-900">{price}</span>
        </div>
      </div>
    </div>
  );
}
