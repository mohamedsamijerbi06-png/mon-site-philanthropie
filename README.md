import React, { useState } from 'react';
import { Heart, Mail, MapPin, Phone, CheckCircle } from 'lucide-react';

export default function PhilanthropyLandingPage() {
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    message: ''
  });

  const [submitted, setSubmitted] = useState(false);

  const handleInputChange = (e) => {
    const { name, value } = e.target;
    setFormData(prev => ({
      ...prev,
      [name]: value
    }));
  };

  const handleSubscribe = () => {
    if (formData.name && formData.email && formData.message) {
      setSubmitted(true);
      setFormData({ name: '', email: '', message: '' });
      setTimeout(() => setSubmitted(false), 5000);
    }
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 via-white to-purple-50">
      {/* Navigation */}
      <nav className="fixed w-full top-0 z-50 bg-white/90 backdrop-blur-md shadow-lg">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
          <div className="flex items-center gap-2">
            <Heart className="w-8 h-8 text-red-500" fill="red" />
            <span className="text-2xl font-bold text-gray-800">PhilanthroHub</span>
          </div>
          <div className="hidden md:flex gap-8">
            <a href="#about" className="text-gray-700 hover:text-blue-600 transition">About</a>
            <a href="#hero" className="text-gray-700 hover:text-blue-600 transition">Hero</a>
            <a href="#achievements" className="text-gray-700 hover:text-blue-600 transition">Achievements</a>
            <a href="#subscribe" className="text-gray-700 hover:text-blue-600 transition">Join Us</a>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section id="hero" className="pt-32 pb-20 px-4 text-center">
        <div className="max-w-4xl mx-auto">
          <h1 className="text-5xl md:text-6xl font-bold text-gray-900 mb-6">
            The Power of <span className="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-purple-600">Philanthropy</span>
          </h1>
          <p className="text-xl text-gray-600 mb-8">
            Discover how generosity and vision can transform the world and change millions of lives for the better.
          </p>
          <button className="bg-gradient-to-r from-blue-600 to-purple-600 text-white px-8 py-4 rounded-lg font-bold text-lg hover:shadow-xl transform hover:scale-105 transition">
            Learn More
          </button>
        </div>
      </section>

      {/* About Philanthropy */}
      <section id="about" className="py-20 px-4 bg-white/50">
        <div className="max-w-4xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-12 text-gray-900">
            What is Philanthropy?
          </h2>
          <p className="text-lg text-gray-700 leading-relaxed mb-6">
            Philanthropy is the voluntary transfer of money, assets, or time to individuals, organizations, or causes 
            for the promotion of the common good. It represents a commitment to making the world a better place through 
            charitable giving and social responsibility.
          </p>
          <p className="text-lg text-gray-700 leading-relaxed">
            Philanthropists dedicate their resources to addressing global challenges such as poverty, disease, education, 
            and environmental conservation. Their impact extends far beyond monetary donations—they inspire social change 
            and create sustainable solutions to complex problems.
          </p>
        </div>
      </section>

      {/* Featured Philanthropist */}
      <section id="featured" className="py-20 px-4">
        <div className="max-w-6xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-16 text-gray-900">
            Featured Philanthropist: <span className="text-blue-600">Bill Gates</span>
          </h2>
          
          <div className="grid md:grid-cols-2 gap-12 items-center">
            {/* Image */}
            <div className="flex justify-center">
              <div className="relative w-80 h-80 rounded-2xl overflow-hidden shadow-2xl border-4 border-blue-100">
                <img 
                  src="https://images.unsplash.com/photo-1595566095178-9ac8209ac715?w=400&h=400&fit=crop" 
                  alt="Bill Gates"
                  className="w-full h-full object-cover"
                />
                <div className="absolute inset-0 bg-gradient-to-br from-blue-500/20 to-purple-500/20"></div>
              </div>
            </div>

            {/* Bio */}
            <div className="space-y-6">
              <div className="bg-gradient-to-r from-blue-50 to-purple-50 p-8 rounded-xl border border-blue-200">
                <h3 className="text-3xl font-bold text-gray-900 mb-4">William Henry Gates III</h3>
                <p className="text-gray-700 mb-4">
                  <strong>Born:</strong> October 28, 1955 (Seattle, Washington)
                </p>
                <p className="text-gray-700 mb-6">
                  Bill Gates is a legendary entrepreneur, software developer, and philanthropist who co-founded Microsoft 
                  and transformed the technology industry. Beyond his tech empire, he is renowned for his unprecedented 
                  commitment to global philanthropy through the Bill & Melinda Gates Foundation.
                </p>
                
                <h4 className="text-2xl font-bold text-gray-900 mb-4">Major Achievements:</h4>
                <div className="space-y-3">
                  <div className="flex gap-3">
                    <CheckCircle className="w-6 h-6 text-green-500 flex-shrink-0" />
                    <p className="text-gray-700"><strong>$50 Billion Commitment:</strong> Pledged over $50 billion to the Bill & Melinda Gates Foundation to combat global poverty, disease, and inequality.</p>
                  </div>
                  <div className="flex gap-3">
                    <CheckCircle className="w-6 h-6 text-green-500 flex-shrink-0" />
                    <p className="text-gray-700"><strong>Vaccine Distribution:</strong> Helped fund and distribute millions of vaccines to combat polio, malaria, HIV/AIDS, and other diseases in developing countries.</p>
                  </div>
                  <div className="flex gap-3">
                    <CheckCircle className="w-6 h-6 text-green-500 flex-shrink-0" />
                    <p className="text-gray-700"><strong>Education Reform:</strong> Invested billions in improving education systems in the United States and globally.</p>
                  </div>
                  <div className="flex gap-3">
                    <CheckCircle className="w-6 h-6 text-green-500 flex-shrink-0" />
                    <p className="text-gray-700"><strong>Agricultural Innovation:</strong> Supported agricultural development in Africa to combat hunger and poverty.</p>
                  </div>
                  <div className="flex gap-3">
                    <CheckCircle className="w-6 h-6 text-green-500 flex-shrink-0" />
                    <p className="text-gray-700"><strong>Climate Action:</strong> Committed significant resources to fighting climate change and developing sustainable technologies.</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Impact Statistics */}
      <section id="achievements" className="py-20 px-4 bg-gradient-to-r from-blue-600 to-purple-600">
        <div className="max-w-6xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-16 text-white">
            Global Impact
          </h2>
          
          <div className="grid md:grid-cols-4 gap-8">
            <div className="bg-white/10 backdrop-blur p-8 rounded-xl text-center border border-white/20">
              <div className="text-4xl font-bold text-white mb-2">140+</div>
              <p className="text-white/90">Countries Reached</p>
            </div>
            <div className="bg-white/10 backdrop-blur p-8 rounded-xl text-center border border-white/20">
              <div className="text-4xl font-bold text-white mb-2">Billions</div>
              <p className="text-white/90">Lives Improved</p>
            </div>
            <div className="bg-white/10 backdrop-blur p-8 rounded-xl text-center border border-white/20">
              <div className="text-4xl font-bold text-white mb-2">330M+</div>
              <p className="text-white/90">Children Vaccinated</p>
            </div>
            <div className="bg-white/10 backdrop-blur p-8 rounded-xl text-center border border-white/20">
              <div className="text-4xl font-bold text-white mb-2">25+</div>
              <p className="text-white/90">Years of Giving</p>
            </div>
          </div>
        </div>
      </section>

      {/* Subscription Form */}
      <section id="subscribe" className="py-20 px-4">
        <div className="max-w-3xl mx-auto">
          <h2 className="text-4xl font-bold text-center mb-4 text-gray-900">
            Join Our Community
          </h2>
          <p className="text-center text-gray-600 mb-12 text-lg">
            Subscribe to learn more about philanthropy and how you can make a difference in the world.
          </p>

          {submitted && (
            <div className="mb-8 p-6 bg-green-50 border-2 border-green-500 rounded-lg flex items-center gap-3">
              <CheckCircle className="w-6 h-6 text-green-600" />
              <div>
                <p className="font-bold text-green-900">Welcome aboard!</p>
                <p className="text-green-800">Your subscription has been confirmed. Check your email!</p>
              </div>
            </div>
          )}

          <div className="bg-gradient-to-br from-blue-50 to-purple-50 p-8 rounded-2xl border-2 border-blue-200 shadow-xl space-y-6">
            <div>
              <label className="block text-gray-800 font-bold mb-2">Full Name</label>
              <input
                type="text"
                name="name"
                value={formData.name}
                onChange={handleInputChange}
                placeholder="Enter your full name"
                className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-blue-600 focus:outline-none transition"
              />
            </div>

            <div>
              <label className="block text-gray-800 font-bold mb-2">Email Address</label>
              <input
                type="email"
                name="email"
                value={formData.email}
                onChange={handleInputChange}
                placeholder="Enter your email"
                className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-blue-600 focus:outline-none transition"
              />
            </div>

            <div>
              <label className="block text-gray-800 font-bold mb-2">Why are you interested?</label>
              <textarea
                name="message"
                value={formData.message}
                onChange={handleInputChange}
                placeholder="Tell us why philanthropy matters to you..."
                rows="5"
                className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-blue-600 focus:outline-none transition resize-none"
              ></textarea>
            </div>

            <button
              onClick={handleSubscribe}
              className="w-full bg-gradient-to-r from-blue-600 to-purple-600 text-white py-4 rounded-lg font-bold text-lg hover:shadow-xl transform hover:scale-105 transition"
            >
              Subscribe Now
            </button>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 text-gray-300 py-12 px-4">
        <div className="max-w-6xl mx-auto">
          <div className="grid md:grid-cols-3 gap-8 mb-8">
            <div>
              <h3 className="text-white font-bold mb-4 flex items-center gap-2">
                <Heart className="w-5 h-5" fill="red" /> PhilanthroHub
              </h3>
              <p className="text-gray-400">Inspiring global change through philanthropy and social responsibility.</p>
            </div>
            <div>
              <h4 className="text-white font-bold mb-4">Quick Links</h4>
              <ul className="space-y-2 text-gray-400">
                <li><a href="#about" className="hover:text-white transition">About</a></li>
                <li><a href="#featured" className="hover:text-white transition">Featured Heroes</a></li>
                <li><a href="#subscribe" className="hover:text-white transition">Join Us</a></li>
              </ul>
            </div>
            <div>
              <h4 className="text-white font-bold mb-4">Contact</h4>
              <div className="space-y-2 text-gray-400">
                <div className="flex items-center gap-2">
                  <Mail className="w-4 h-4" /> info@philanthropub.com
                </div>
                <div className="flex items-center gap-2">
                  <Phone className="w-4 h-4" /> +1 (555) 123-4567
                </div>
              </div>
            </div>
          </div>
          <div className="border-t border-gray-700 pt-8 text-center text-gray-400">
            <p>&copy; 2025 PhilanthroHub. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  );
}
